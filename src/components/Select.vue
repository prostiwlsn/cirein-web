<script setup>
const props = defineProps({
    isActive: Boolean
})
</script>

<template>
    <Transition>
        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="isActive">
            <path d="M10.0001 4.16663V15.8333M4.16675 9.99996H15.8334" stroke="#F3F3F3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
    </Transition>
</template>

<style scoped lang="scss">
.v-enter-active,
.v-leave-active {
  transition: opacity 0.3s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}
</style>