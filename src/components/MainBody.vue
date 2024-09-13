<script setup>
import Select from './Select.vue';
</script>

<template>
    <div class="outer">
        <div class="text">
            <h1>Xdxdxd</h1>
            <div>sex</div>
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

        h1,
        h2,
        h3,
        h4,
        h5,
        h6 {
            margin: 0;
            font-weight: 400;
        }
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