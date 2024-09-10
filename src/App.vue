<script setup>
import { ref } from 'vue';
import Links from './components/Links.vue';

//https://www.figma.com/design/FSJKBCHKplqtkyuMUmZDhi/Untitled?m=auto&t=OKZg5P8dyu6mDnhk-6

const pages = ref(["HOME", "ABOUT", "CONTACT"])
</script>

<template>
  <Links :pages="pages"></Links>
</template>

<style scoped>
</style>
