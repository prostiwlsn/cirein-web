<script setup>
import { ref } from 'vue';
import Link from './Link.vue';

defineProps({
    pages: Array //[{name: String, isActive: Boolean}]
}

)

const isActive = ref(false)
</script>

<template>
    <Link v-model="isActive">HOME</Link>
    <button @click="isActive=false">xddd</button>
</template>

<style scoped>
</style>