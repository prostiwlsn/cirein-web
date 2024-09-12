<script setup>
import { ref } from 'vue';
import Select from './Select.vue'; 
//69

const props = defineProps({
    isActive: Boolean
})
</script>

<template>
    <div :class="isActive ? 'active' : ''" class="link">
        <slot></slot>

        <Select class="tr-corner" :isActive="isActive"/>
        <Select class="tl-corner" :isActive="isActive"/>
        <Select class="br-corner" :isActive="isActive"/>
        <Select class="bl-corner" :isActive="isActive"/>
    </div>
</template>

<style scoped lang="scss">
.link {
    position: relative; 
    font-size: 19px; 
    width: min-content; 
    cursor: pointer;

    margin-left: 2em;
    margin-right: 2em;

    transition: all;
    transition-duration: 300ms;

    &:hover {
        color: #adf576;
    }
}

.active {
    color: #72C134 !important; 
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