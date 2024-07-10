<template>
    <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 gap-8">
        <div v-for="movie in movies" :key="movie" class="border rounded-md shadow-md">
            <img :src="movie.Images[0]" :alt="movie.Title" class="h-80 md:h-60 w-full object-cover rounded-t-md">
            
            <section class="details p-6 flex flex-col gap-2">
                <h2 class="font-medium flex flex-row justify-between text-2xl">
                    {{ movie.Title }}

                    <span 
                        class="bg-gray-100 text-gray-800 rounded h-fit text-sm font-medium me-2 px-2.5 py-0.5"
                    >
                        {{ movie.Rated }}
                    </span>
                </h2>
                <div class="flex flex-row gap-4 mb-4">
                    <p>{{ movie.Genre }}</p>
                    <span>&#x2022;</span>
                    <p>{{ movie.Runtime }}</p>
                </div>

                <p>{{ movie.Released }}</p>

            </section>
        </div>
        
    </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';
import MovieCard from '../components/MovieCard.vue'

const movies = ref<[]>([]);

onMounted(async () => {
   try {
    const resp = await fetch('https://api.npoint.io/5d772753d74a6a58a599');
    const data = await resp.json();

    movies.value = data;
    console.log(movies.value);
   } catch(error) {
    console.log('Error');
   }
})
</script>