<template>
    <div>
        {{ movie.Title }}
    </div>
</template>

<script setup lang="ts">

const props = defineProps<{
    movie: any
}>();
</script>