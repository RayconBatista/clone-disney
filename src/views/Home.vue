<template>
  <div class="container mx-auto">
    <div class="my-8">
      <vue-glide :perView="1" :bullet="true" class="mb-12">
        <vue-glide-slide v-for="(item, index) in movies" :key="index">
          <router-link :to="item.url">
            <img :src="item.image" :alt="item.name" class="rounded" />
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

      <card-category></card-category>

      <recommended></recommended>
      
    </div>
  </div>
</template>

<script>
import movies from "@/assets/dic/news.js";
import CardCategory from '@/components/CardCategory';
import Recommended from '@/components/Recommended';
export default {
  name: "Home",

  data() {
    return {
      movies: movies.news,
    };
  },
  components: {
    CardCategory,
    Recommended
  }
};
</script>
