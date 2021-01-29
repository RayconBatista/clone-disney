<template>
  <div>
    <div class="recommended px-6 mb-12">
      <h3 class="text-gray-500 mb-1">Recomendado para você</h3>

      <vue-glide
        :perView="5"
        :gap="20"
        :peek="{ before: 0, after: 70 }"
        :breakpoints="{
          1024: { perView: 3 },
          800: { perView: 2 },
          576: { perView: 1, peek: { before: 0, after: 0 } },
        }"
        class="mb-12"
      >
        <vue-glide-slide
          v-for="(recommended, index) in recommendeds"
          :key="index"
        >
          <router-link to="#">
            <img :src="recommended.image" :alt="recommended.name" />
          </router-link>
        </vue-glide-slide>
        <template slot="control">
          <button
            data-glide-dir="<"
            class="absolute w-8 h-8 rounded-full bg-gray-500"
            style="top: calc(50% - 16px); left: 18px"
          >
            <i class="fas fa-chevron-left"></i>
          </button>
          <button
            data-glide-dir=">"
            class="absolute w-8 h-8 rounded-full bg-gray-500"
            style="top: calc(50% - 16px); right: 10px"
          >
            <i class="fas fa-chevron-right"></i>
          </button>
        </template>
      </vue-glide>
    </div>

    <div class="recommended px-6 mb-12">
      <h2 class="text-gray-500 mb-1">Continue Assistindo</h2>
      <vue-glide
        :perView="5"
        :gap="20"
        :peek="{ before: 0, after: 70 }"
        class="mb-12"
      >
        <vue-glide-slide v-for="(watched, index) in watchings" :key="index">
          <router-link to="#">
            <img :src="watched.image" :alt="watched.name" />
          </router-link>
        </vue-glide-slide>
        <template slot="control">
          <button
            data-glide-dir="<"
            class="absolute w-8 h-8 rounded-full bg-gray-500"
            style="top: calc(50% - 16px); left: 18px"
          >
            <i class="fas fa-chevron-left"></i>
          </button>
          <button
            data-glide-dir=">"
            class="absolute w-8 h-8 rounded-full bg-gray-500"
            style="top: calc(50% - 16px); right: 10px"
          >
            <i class="fas fa-chevron-right"></i>
          </button>
        </template>
      </vue-glide>
    </div>
  </div>
</template>
<script>
// @ is an alias to /src
import rec from "@/assets/dic/recommendeds.js";
import watch from "@/assets/dic/watchings.js";
export default {
  name: "Home",

  data() {
    return {
      recommendeds: rec.recommendeds,
      watchings: watch.watchings,
    };
  },
};
</script>