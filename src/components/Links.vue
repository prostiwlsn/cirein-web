<script setup>
import { ref, onMounted } from 'vue';
import Link from './Link.vue';

const props = defineProps({
    pages: Array
})

const isActive = ref([])
const activePageIndex = ref(0)

function isActiveOnClick(index){
    isActive.value[activePageIndex.value] = false

    activePageIndex.value = index
    isActive.value[index] = true
}

onMounted(() => {
    props.pages.forEach(element => {
        isActive.value.push(false)
    });

    isActive.value[activePageIndex.value] = true;
})
</script>

<template>
    <Link v-for="(page, index) in pages" :isActive="isActive[index]" @click="() => isActiveOnClick(index)">{{page}}</Link>
</template>

<style scoped>
</style>