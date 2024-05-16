<template>
    <div class="flex">
        <div class="">
<h1 class="text-gray-500 font-light">{{title}}</h1>
<h4 class="font-bold text-black text-3xl">{{subhead}}</h4>
<p>{{text}}</p>
        </div>

    </div>
</template>

<script setup>
import { _descriptors } from 'chart.js/helpers';

const props = defineProps({
    title : String,
    subhead: String,
    text: String
})
</script>

<style lang="scss" scoped>

</style>