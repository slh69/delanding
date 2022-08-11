<template>
  <div class="pb-6">
    <h2
      class="font- text-center font-bold text-cyan-400 tracking-tight sm:text-4xl"
    >
      Meet Your Pure Chiro Now Chiropractors
    </h2>
  </div>
   <ul role="list" class="mx-auto grid grid-cols-2 gap-x-4 gap-y-8 sm:grid-cols-4 md:gap-x-6  xl:grid-cols-3">
          <li class="text-center" >
            <div class="space-y-4">
            <img
            class="mx-auto h-20 w-20 rounded-full"
            src="../assets/docHoskins.png"
            alt=""
          />
              <div class="space-y-2">
                <div class="text-xs lg:text-sm">
                  <h3 class="font-semibold">Dwayne Hoskins</h3>
                  <p class="text-indigo-600">Chiropractor</p>
                  <p class="text-indigo-600">Gentle Giant of Chiropractic</p>
                </div>
              </div>
            </div>
          </li>
          <li class="text-center" >
            <div class="space-y-4">
            <img
            class="mx-auto h-20 w-20 rounded-full"
            src="../assets/samRalls.png"
            alt=""
          />
              <div class="space-y-2">
                <div class="text-xs lg:text-sm">
                  <h3 class="font-semibold">Sam Ralls</h3>
                  <p class="text-indigo-600">Chiropractor</p>
                  <p class="text-indigo-600">Family & Sports Chiropractic</p>
                </div>
              </div>
            </div>
          </li>
          <li class="text-center" >
            <div class="space-y-4">
            <img
            class="mx-auto h-20 w-20 rounded-full"
            src="../assets/tomMedlin.png"
            alt=""
          />
              <div class="space-y-2">
                <div class="text-xs lg:text-sm">
                  <h3 class="font-semibold">Tom Medlin</h3>
                  <p class="text-indigo-600">Chiropractor</p>
                  <p class="text-indigo-600">Family Chiropractor</p>
                </div>
              </div>
            </div>
          </li>
        </ul>


  <div class="grid items-center">
    <div>
      <h1 class="font-bold text-center pt-10 pb-4">Your Upcoming Appointments</h1>
    </div>
  </div>

  <div
    class="border-gray-100 p-2 mt-2 mr-3 ml-2 rounded-l shadow-md mx-auto bg-blue-100"
  >
    <h4 class="text-sm font-bold">July 20 4:00 pm</h4>
    <p class="text-xs color-gray-200">Sam Smith</p>
    <p class="text-xs color-gray-200">with Dr Hoskins</p>
  </div>

  <div
    class="border-gray-100 p-2 mt-2 mr-3 ml-2 rounded-l shadow-md mx-auto bg-yellow-100"
  >
    <h4 class="text-sm font-bold">July 20 4:10 pm</h4>
    <p class="text-xs color-gray-200">Mrs. Sam Smith</p>
    <p class="text-xs color-gray-200">with Dr Sam</p>
  </div>

  <div
    class="border-gray-100 p-2 mt-2 mr-3 ml-2 rounded-l shadow-md mx-auto bg-blue-100"
  >
    <h4 class="text-sm font-bold">July 20 4:30 pm</h4>
    <p class="text-xs color-gray-200">Sam Smith JR</p>
    <p class="text-xs color-gray-200">with Dr Hoskins</p>
  </div>

  <div
    class="border-gray-100 p-2 mt-2 mr-3 ml-2 rounded-l shadow-md mx-auto bg-green-100"
  >
    <h4 class="text-sm font-bold">July 20 4:40 pm</h4>
    <p class="text-xs color-gray-200">Samantha Smith</p>
    <p class="text-xs color-gray-200">with Dr Medlin</p>
  </div>
</template>

<script setup>
import docHoskins from '../assets/docHoskins.png'
import samRalls from '../assets/samRalls.png'
import tomMedlin from '../assets/tomMedlin.png'

const people = [
  {
    id: 1,
    name: "Dwayne Hoskins",
    title: "Chiropractor",
    subtitle: "Gentle Giant of Chiropractic",
    photo: 'docHoskins',
  },
    {
    id: 2,
    name: "Sam Ralls",
    title: "Chiropractor",
    subtitle: "Family & Sports Chiropractor",
    photo: 'samRalls',
  },
    {
    id: 1,
    name: "Tom Medlin",
    title: "Chiropractor",
    subtitle: "Family Chiropractor",
    photo: 'tomMedlin',
  },
];


</script>
