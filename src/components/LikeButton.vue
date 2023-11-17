<script setup>
import { computed } from '@vue/reactivity';
import { ref } from 'vue';

const counter = ref(0);
const colors= ref(['purple','blue','green','yellow','orange','red']);

const updateCounter = ()=>{
    counter.value ++;
}

const currentColor = computed(() => colors.value[counter.value]);

</script>


<template>

<div>
    <button :style="{backgroundColor: currentColor}" @click="updateCounter()">Likes {{ counter }}</button>

    <button v-bind:style="{backgroundColor: colors[counter]}" v-on:click="counter++">Likes {{ counter }}</button>

</div>

</template>


<style scoped>
</style>