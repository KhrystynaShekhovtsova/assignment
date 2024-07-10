<template>
  <div>
    <div class="bg-gray-100 shadow-sm mb-8">
      <header class="py-6 container mx-auto">
        <h1 class="text-2xl">Movies List</h1>
      </header>
    </div>
    

    <div class="container mx-auto">
      <MovieListings></MovieListings>
    </div> 
  </div>
</template>

<script setup lang="ts">
import MovieListings from '@/components/MovieListings.vue';

</script>


<style scoped>

</style>
