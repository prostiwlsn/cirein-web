<script setup>
import Links from './Links.vue';

const props = defineProps({
    pages: Array
})
</script>

<template>
    <div class="navbar">
        <div>xdd</div>
        <Links :pages="pages"/>
        <div>xdd</div>
    </div>
</template>

<style scoped lang="scss">
.navbar {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: 1200px;

    @media screen and (max-width: 1080px) {
        width: 100%;
    }
}
</style>