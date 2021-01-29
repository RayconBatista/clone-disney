<template>
  <div class="categories flex items-center mb-12 mx-4">
    <div
      class="w-1/5 px-4 rounded"
      v-for="(category, index) in categories"
      :key="index"
      :breakpoints="{
        1024: { perView: 3 },
        800: { perView: 2 },
        576: { perView: 1, peek: { before: 0, after: 0 } },
      }"
    >
      <a
        :href="category.url"
        class="bg-gray-800 h-32 flex justify-center items-center rounded-lg border border-gray-700 shadow-custom p-4 hover:bg-gray-900"
      >
        <img :src="category.image" :alt="category.name" />
      </a>
    </div>
  </div>
</template>
<script>
import list from "@/assets/dic/categories.js";
export default {
  name: "Home",

  data() {
    return {
      categories: list.categories,
    };
  },
};
</script>
