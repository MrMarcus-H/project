<script setup>
import { reactive } from "vue";
import Header from "./components/Header.vue";
import Wheather from "./components/Wheather.vue";

const searchTerm = reactive({
  query: "",
  timeout: null,
  result: null,
});

const handleSearch = () => {
  clearTimeout(searchTerm.timeout);
  searchTerm.timeout = setTimeout(async () => {
    if (searchTerm.query != "") {
      const res = await fetch(
        `http://api.weatherapi.com/v1/search.json?key=532cfd7349ff4dacadf154539241206&q=${searchTerm.query}`
      );

      const data = await res.json();
      searchTerm.result = data;
    } else {
      searchTerm.result = null;
    }
  }, 500);
};

const getWeather = async (id) => {
  const res = await fetch(
    `http://api.weatherapi.com/v1/forecast.json?key=532cfd7349ff4dacadf154539241206&q=id:${id}&days=3&aqi=no&alerts=no`
  );

  const data = await res.json();
  console.log(data);
};
</script>

<template>
  <header class="w-fit leading-3">
    <div class="flex h-full w-fit flex-wrap justify-center items-start">
      <Header></Header>
    </div>
  </header>

  <main class="w-full h-full">
    <form class="flex items-center gap-3 w-[80%]">
      <input
        type="text"
        class="p-3 w-[100%] h-fit rounded-xl bg-[#202b3c] text-white placeholder:text-gray-300"
        placeholder="Search for cities"
        v-model="searchTerm.query"
        @input="handleSearch"
      />
      <button class="h-fit bg-[#0396fb] text-white py-2 rounded-md px-4">
        Search
      </button>
    </form>

    <div
      v-if="searchTerm.query !== null"
      class="bg-black my-2 rounded-lg shadow-lg w-[80%]"
    >
      <div v-for="place in searchTerm.result">
        <button
          @click="getWeather(place.id)"
          :key="place.id"
          class="px-3 my-2 hover:text-indigo-600 hover:font-bold w-[80%] text-left"
        >
          {{ place.name }}, {{ place.region }}, {{ place.country }}
        </button>
      </div>
    </div>

    <Wheather></Wheather>
  </main>
</template>

<script>
export default (await import("vue")).defineComponent({
  name: "App",

  components: {
    Header,
  },

  data() {
    return {
      city: "",
      showWheather: false,
    };
  },

  methods: {
    async searchWheather() {
      this.showWheather = false;
      await this.$nextTick();
      this.showWheather = true;
    },
  },
});
</script>
