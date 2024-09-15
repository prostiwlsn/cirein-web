<script setup>
import { ref, onMounted } from 'vue';
import Link from './Link.vue';
import { selectedPage } from '../composables/selectedPage';

const props = defineProps({
    pages: Array
})

const isActive = ref([])
const activePageIndex = ref(0)

function isActiveOnClick(index, pageName){
    isActive.value[activePageIndex.value] = false

    activePageIndex.value = index
    isActive.value[index] = true

    selectedPage.name = pageName;
}

onMounted(() => {
    props.pages.forEach(element => {
        isActive.value.push(false)
    });

    isActive.value[activePageIndex.value] = true;
    selectedPage.name = props.pages[0];
})
</script>

<template>
    <div class="links">
        <Link v-for="(page, index) in pages" :isActive="isActive[index]" @click="() => isActiveOnClick(index, page)">{{page}}</Link>
    </div>
</template>

<style scoped>
.links {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}
</style>