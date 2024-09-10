<script setup>
import { ref } from 'vue';
import Select from './Select.vue';

const isActive = defineModel()

//xdd
</script>

<template>
    <div :class="isActive ? 'active' : ''" @click="isActive = true" style="position: relative;">
        <slot></slot>
        <Select class="tr-corner" v-if="isActive"/>
        <Select class="tl-corner" v-if="isActive"/>
        <Select class="br-corner" v-if="isActive"/>
        <Select class="bl-corner" v-if="isActive"/>
    </div>
</template>

<style scoped>
.active {
    color: #72C134
}

.tr-corner{
    position: absolute;
    top: 0px;
    right: 0px;
}

.tl-corner{
    position: absolute;
    top: 0px;
    left: 0px;
}

.br-corner{
    position: absolute;
    bottom: 0px;
    right: 0px;
}

.bl-corner{
    position: absolute;
    position: absolute;
    bottom: 0px;
    left: 0px;
}
</style>