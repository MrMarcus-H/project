<script setup>
import temperature from "./icons/temperature.svg";
import sea from "./icons/sea.svg";
import wind from "./icons/wind.svg";
import raindrops from "./icons/raindrops.svg";
</script>

<template>
  <section class="flex pb-8">
    <section class="flex flex-col gap-4 w-[80%]">
      <div class="m-7">
        <div>
          <h1 class="text-white text-3xl font-bold">Madrid</h1>
          <p class="mt-2">Weather condition: 0%</p>

          <h1 class="text-white text-[3.5rem] font-bold mt-10">21°</h1>
        </div>

        <div>
          <div></div>
        </div>
      </div>

      <div class="bg-[#202b3c] px-7 py-6 rounded-xl">
        <p class="mb-4">TODAY'S FORECAST</p>
        <div class="mt-3 px-4 flex gap-5">
          <ul
            class="flex gap-2 flex-col justify-center items-center border-r-2 border-gray-700 pr-4"
          >
            <li>6:00 AM</li>
            <li>icon</li>
            <li class="font-bold text-white text-2xl">25&deg;</li>
          </ul>

          <ul
            class="flex gap-2 flex-col justify-center items-center border-r-2 border-gray-700 pr-4"
          >
            <li>6:00 AM</li>
            <li>icon</li>
            <li class="font-bold text-white text-2xl">32&deg;</li>
          </ul>

          <ul
            class="flex gap-2 flex-col justify-center items-center border-r-2 border-gray-700 pr-4"
          >
            <li>6:00 AM</li>
            <li>icon</li>
            <li class="font-bold text-white text-2xl">27&deg;</li>
          </ul>
        </div>
      </div>

      <div class="bg-[#202b3c] px-7 py-6 rounded-xl">
        <div class="flex justify-between items-center mb-4">
          <p>AIR CONDITIONS</p>
          <button
            class="text-white bg-[#0396fb] pt-[7px] pb-2 px-4 text-sm rounded-full"
          >
            See more
          </button>
        </div>
        <div class="mt-3 px-4 grid gap-5 grid-cols-2 grid-rows-2">
          <ul class="flex gap-2">
            <li><img :src="temperature" class="w-4" /></li>
            <li class="flex flex-col gap-1">
              <p class="text-base">Real Feel</p>
              <p class="font-bold text-white text-3xl">30&deg;</p>
            </li>
          </ul>

          <ul class="flex gap-2">
            <li><img :src="wind" class="w-6" /></li>
            <li class="flex flex-col gap-1">
              <p class="text-base">Wind</p>
              <p class="font-bold text-white text-3xl">0.2 km/h</p>
            </li>
          </ul>

          <ul class="flex gap-2 ml-[-6px]">
            <li><img :src="raindrops" class="w-6 mt-[2px]" /></li>
            <li class="flex flex-col gap-1">
              <p class="text-base">Humidity</p>
              <p class="font-bold text-white text-3xl">38%</p>
            </li>
          </ul>

          <ul class="flex gap-2">
            <li><img :src="sea" class="w-6" /></li>
            <li class="flex flex-col gap-1">
              <p class="text-base">Sea Level</p>
              <p class="font-bold text-white text-3xl">0%</p>
            </li>
          </ul>
        </div>
      </div>
    </section>

    <section class="w-[50rem] pb-7">
      <div class="bg-[#202b3c] px-9 h-full py-10 rounded-xl m-7">
        <p class="mb-7">5-DAY FORECAST</p>
        <div class="mt-3 px-4 flex flex-col gap-5">
          <ul
            class="flex gap-2 justify-between items-center border-b-2 border-gray-700 pb-8"
          >
            <li>Mon</li>
            <li class="flex gap-3">
              <img src="" alt="icon" />
              <p class="text-white">Sunny</p>
            </li>
            <li>25</li>
          </ul>

          <ul
            class="flex gap-2 justify-between items-center border-b-2 border-gray-700 pb-8"
          >
            <li>Tue</li>
            <li class="flex gap-3">
              <img src="" alt="icon" />
              <p class="text-white">Sunny</p>
            </li>
            <li>26</li>
          </ul>

          <ul
            class="flex gap-2 justify-between items-center border-b-2 border-gray-700 pb-8"
          >
            <li>Wed</li>
            <li class="flex gap-3">
              <img src="" alt="icon" />
              <p class="text-white">Cloudy</p>
            </li>
            <li>14</li>
          </ul>

          <ul
            class="flex gap-2 justify-between items-center border-b-2 border-gray-700 pb-8"
          >
            <li>Thu</li>
            <li class="flex gap-3">
              <img src="" alt="icon" />
              <p class="text-white">Sunny</p>
            </li>
            <li>21</li>
          </ul>

          <ul class="flex gap-2 justify-between items-center">
            <li>Fri</li>
            <li class="flex gap-3">
              <img src="" alt="icon" />
              <p class="text-white">Storm</p>
            </li>
            <li>16</li>
          </ul>
        </div>
      </div>
    </section>
  </section>
</template>

<script>
export default (await import("vue")).defineComponent({
  name: "Wheather",
  components: {},
});
</script>

<style scoped></style>
