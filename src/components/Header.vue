<template>
  <div class=" w-full py-2 px-5 bg-[#202b3c] rounded-2xl flex flex-row gap-7 justify-center items-center">
    <img src="../assets/logo.png" class="mr-5 w-10">

    <a class="flex gap-2  flex-row items-center justify-center p-0 hover:bg-transparent">
      <i class="fa fa-cloud text-white text-2xl cursor-pointer"></i>
      <p class="text-white cursor-pointer">Weather</p>
    </a>

    <a class="flex gap-2 flex-row items-center justify-center p-0 hover:bg-transparent">
      <i class="fa fa-building text-gray-300 text-2xl cursor-pointer"></i>
      <p class="text-gray-300 cursor-pointer">Cities</p>
    </a>

    <a class="flex gap-2 flex-row items-center justify-center p-0 hover:bg-transparent">
      <i class="fa fa-map text-gray-300 text-2xl cursor-pointer"></i>
      <p class="text-gray-300 cursor-pointer">Map</p>
    </a>

    <a class="flex gap-2 flex-row items-center justify-center p-0 hover:bg-transparent">
      <i class="fa fa-sliders text-gray-300 text-2xl cursor-pointer"></i>
      <p class="text-gray-300 cursor-pointer">Settings</p>
    </a>
  </div>
</template>

<script>
  export default ( await import('vue')).defineComponent ({
    name: 'Header',

    components: {
   },
  })
</script>

<style scoped>


</style>
