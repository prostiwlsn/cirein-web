<script setup>
import { ref, onMounted } from 'vue';

import Links from './Links.vue';
import Logo from './Logo.vue';

const props = defineProps({
    pages: Array
})

const logoRef = ref(null)
const emptyRef = ref(null)

onMounted(() => {
    //console.log(logoRef.value.offsetWidth)
    //console.log(emptyRef.value)
    emptyRef.value.style.width = logoRef.value.offsetWidth + "px"
    //console.log(emptyRef.value.offsetWidth)
})
</script>

<template>
    <div class="navbar">
        <div ref="logoRef"><Logo/></div>
        <Links :pages="pages"/>
        <div ref="emptyRef"></div>
    </div>
</template>

<style scoped lang="scss">
.navbar {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 1200px;

    @media screen and (max-width: 1200px) {
        width: 100%;
    }
}
</style>