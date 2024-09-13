<script setup>
import { ref, onMounted } from 'vue';
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
import MainBody from './components/MainBody.vue';

//https://www.figma.com/design/FSJKBCHKplqtkyuMUmZDhi/Untitled?m=auto&t=OKZg5P8dyu6mDnhk-6

const pages = ref(["HOME", "ABOUT", "CONTACT"])

const navbar = ref(null)
const mainBody = ref(null)
const footer = ref(null)

onMounted(() => {
  mainBody.value.style.marginTop = navbar.value.offsetHeight + "px";
  mainBody.value.style.minHeight = window.innerHeight - navbar.value.offsetHeight - footer.value.offsetHeight + "px";
})
</script>

<template>
  <div class="top-bar" ref="navbar">
    <Navbar :pages="pages"/>
  </div>

  <div class="main-body" ref="mainBody">
    <MainBody/>
  </div>

  <div class="bottom-bar" ref="footer">
    <Footer/>
  </div>
</template>

<style scoped>
.top-bar {
  display: flex;
  justify-content: center;
  width: 100%;
  position: fixed;
  left: 0;
  top: 0;
}

.main-body {
  display: flex;
  justify-content: center;
  width: 100%;
}

.bottom-bar {
  width: 100%;
}
</style>
