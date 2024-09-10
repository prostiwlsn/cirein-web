<script setup>
import { ref } from 'vue';
import Select from './Select.vue';

const isActive = defineModel()
</script>

<template>
    <div :class="isActive ? 'active' : ''" @click="isActive = true" style="position: relative; font-size: 19px; width: min-content; cursor: pointer;">
        <slot></slot>
        <Select class="tr-corner" v-if="isActive"/>
        <Select class="tl-corner" v-if="isActive"/>
        <Select class="br-corner" v-if="isActive"/>
        <Select class="bl-corner" v-if="isActive"/>
    </div>
</template>

<style scoped>
.active {
    color: #72C134;
}

.tr-corner{
    position: absolute;
    top: 0px;
    right: 0px;

    margin-top: -15px;
    margin-right: -29px;
}

.tl-corner{
    position: absolute;
    top: 0px;
    left: 0px;

    margin-top: -15px;
    margin-left: -29px;
}

.br-corner{
    position: absolute;
    bottom: 0px;
    right: 0px;

    margin-bottom: -15px;
    margin-right: -29px;
}

.bl-corner{
    position: absolute;
    bottom: 0px;
    left: 0px;

    margin-bottom: -15px;
    margin-left: -29px;
}
</style>