<template>
  <div class=" max-w-7xl h-screen border-2 border-gray-300 mx-auto">
    <div class="w-full h-28 bg-white">
      <LogoComponent />
    </div>
    <div class="lg:flex">
    <div class="w-full lg:w-1/2 bg-white border-r-2 border-gray-200 h-screen">
      <!--staff info and office message-->
      <div>
        <Message />
      </div>
      <div>
       <OfficeMessage />
      </div>

    </div>
    <div class="w-full lg:w-1/2 bg-white h-screen mx-auto">
      <!--Appt calendar and list of appts-->
      <div>
      <Calendar />
      </div>
      <div class="flex justify-center" >
      <ApptButton  />

      </div>
    </div>

    </div>

  </div>
</template>

<script setup>
import Calendar from "./components/Calendar.vue";
import OfficeMessage from "./components/OfficeMessage.vue";
import LogoComponent from "./components/LogoComponent.vue";
import Message from "./components/Message.vue";
import ApptButton from "./components/ApptButton.vue";

</script>
