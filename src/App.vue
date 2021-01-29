<template>
  <div id="app" class="flex bg-gray-900 text-white min-h-screen">
    <div class="w-full">
      <div class="container mx-auto">
        <router-view />
      </div>
    </div>
  </div>
</template>
<script>
// import NavBar from "@/components/NavBar";
export default {
  components: {
    // NavBar,
  },
};
</script>
