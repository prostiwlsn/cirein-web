<script setup>
import Select from './Select.vue';
import { selectedPage } from '../composables/selectedPage';
import { watch } from 'vue';

import ABOUT from './pages/ABOUT.vue';
import CONTACT from './pages/CONTACT.vue';
import HOME from './pages/HOME.vue';

const components = {
    ABOUT,
    CONTACT,
    HOME
};
</script>

<template>
    <div class="outer">
        <div class="text">
            <component :is="components[selectedPage.name]"></component>
        </div>
        <Select class="tr-corner" :isActive="true"/>
        <Select class="tl-corner" :isActive="true"/>
        <Select class="br-corner" :isActive="true"/>
        <Select class="bl-corner" :isActive="true"/>
    </div>
</template>

<style lang="scss" scoped>
.outer {
    width: 95%;
    position: relative;
    height: fit-content;

    display: flex;
    justify-content: center;

    .text {
        width: 95%;
        margin-bottom: 2em;
        margin-top: 2em;

        text-align: left;

        text-shadow: 1px 1px 2px black;
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
        bottom: 0px;
        left: 0px;
    }
}

</style>