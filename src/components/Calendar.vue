<template>
 <div
            class="hidden mx-auto max-w-md flex-none border-l border-gray-100 py-10 px-8 md:block"
          >
            <div class="flex items-center text-center text-gray-900">
              <button
                type="button"
                @click="lastMonth"
                class="-m-1.5 flex flex-none items-center justify-center p-1.5 text-gray-400 hover:text-gray-500"
              >
                <span class="sr-only">Previous month</span>
                <ChevronLeftIcon class="h-5 w-5" aria-hidden="true" />
              </button>
              <div class="flex-auto font-semibold">{{ currentMonth }}</div>
              <button
                type="button"
                @click="nextMonth"
                class="-m-1.5 flex flex-none items-center justify-center p-1.5 text-gray-400 hover:text-gray-500"
              >
                <span class="sr-only"></span>
                <ChevronRightIcon class="h-5 w-5" aria-hidden="true" />
              </button>
            </div>
            <div
              class="mt-6 grid grid-cols-7 text-center text-xs leading-6 text-gray-500"
            >
              <div>S</div>
              <div>M</div>
              <div>T</div>
              <div>W</div>
              <div>T</div>
              <div>F</div>
              <div>S</div>
            </div>
            <div
              class="isolate mt-2 grid grid-cols-7 gap-px rounded-lg "
            >
              <button
                v-for="(day, dayIdx) in days"
                :key="day.toString()"
                type="button"
                @click="setSelectedDay(day)"
                :class="[
                  'py-1.5 hover:bg-gray-100 focus:z-10',
                  isSameMonth(day, today) ? 'bg-white' : 'bg-gray-50',
                  (isEqual(day, selectedDay) || isToday(day)) &&
                    'font-semibold',
                  isEqual(day, selectedDay) && 'text-white',
                  !isEqual(day, selectedDay) &&
                    isSameMonth(day, firstDayCurrentMonth) &&
                    !isToday(day) &&
                    'text-gray-900',
                  !isEqual(day, selectedDay) &&
                    !isSameMonth(day, firstDayCurrentMonth) &&
                    !isToday(day) &&
                    'text-gray-400',
                  isToday(day) &&
                    !isEqual(day, selectedDay) &&
                    'text-indigo-600',
                  dayIdx === 0 && 'rounded-tl-lg',
                  dayIdx === 6 && 'rounded-tr-lg',
                  dayIdx === days.length - 7 && 'rounded-bl-lg',
                  dayIdx === days.length - 1 && 'rounded-br-lg',
                ]"
              >
                <time
                  :datetime="format(day, 'MMMM-dd-yyyy')"
                  :class="[
                    'mx-auto flex h-7 w-7 items-center justify-center rounded-full',
                    isEqual(day, selectedDay) &&
                      isToday(day) &&
                      'bg-indigo-600',
                    isEqual(day, selectedDay) && !isToday(day) && 'bg-gray-900',
                  ]"
                >
                  {{ format(day, "d") }}
                </time>
              </button>
              <div class="w-1 h-1 bg-cyan-500 rounded-full mx-auto mt-1"></div>
              
            </div>
          </div>
</template>

<script setup>
import { ref,reactive, onMounted, computed } from "vue";
import {
  ChevronDownIcon,
  ChevronLeftIcon,
  ChevronRightIcon,
  DotsHorizontalIcon,
  DotsVerticalIcon
} from "@heroicons/vue/solid";
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/vue";
import {
  eachDayOfInterval,
  endOfMonth,
  format,
  startOfMonth,
  addMonths,
  startOfToday,
  endOfWeek,
  isToday,
  isSameMonth,
  isEqual,
  add,
  parse,
  parseISO,
  compareAsc,
  getUnixTime
} from "date-fns";
import { useState } from "../state/state.js";
let today = startOfToday();
let [selectedDay, setSelectedDay] = useState(today);
let [currentMonth, setCurrentMonth] = useState(format(today, "MMM-yyyy"));
let firstDayCurrentMonth = ref(
  parse(currentMonth.value, "MMM-yyyy", new Date())
);
console.log("FDCM outside", firstDayCurrentMonth.value);
let currentMonthStartDay = -firstDayCurrentMonth.value.getDay();
let days = ref(
  eachDayOfInterval({
    start: add(firstDayCurrentMonth.value, { days: currentMonthStartDay }),
    end: endOfWeek(endOfMonth(firstDayCurrentMonth.value)),
  })
);
const nextMonth = () => {
  let firstDayCurrentMonth = ref(
    parse(currentMonth.value, "MMM-yyyy", new Date())
  );
  let firstDayNextMonth = add(firstDayCurrentMonth.value, { months: 1 });
  setCurrentMonth(format(firstDayNextMonth, "MMM-yyyy"));
  currentMonthStartDay = -firstDayNextMonth.getDay();
  days.value = eachDayOfInterval({
    start: add(firstDayNextMonth, { days: currentMonthStartDay }),
    end: endOfWeek(endOfMonth(firstDayNextMonth)),
  });
};
const lastMonth = () => {
  let firstDayCurrentMonth = parse(currentMonth.value, "MMM-yyyy", new Date());
  let firstDayLastMonth = add(firstDayCurrentMonth, { months: -1 });
  setCurrentMonth(format(firstDayLastMonth, "MMM-yyyy"));
  currentMonthStartDay = -firstDayLastMonth.getDay();
  days.value = eachDayOfInterval({
    start: add(firstDayLastMonth, { days: currentMonthStartDay }),
    end: endOfWeek(endOfMonth(firstDayLastMonth)),
  });
};
</script>