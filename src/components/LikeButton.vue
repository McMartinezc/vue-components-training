<script setup>
import { computed } from '@vue/reactivity';
import { ref } from 'vue';

const counter = ref(0);
const colors= ref(['purple','blue','green','yellow','orange','red']);

const updateCounter = ()=>{
    counter.value ++;
}

const currentColor = computed(() => colors.value[counter.value % colors.value.length]);

</script>


<template>

<div>
    <button v-bind:style="{backgroundColor: currentColor}" @click="updateCounter()">Likes {{ counter }}</button>

    <button v-bind:style="{backgroundColor: colors[counter % colors.length]}" v-on:click="counter++">Likes {{ counter }}</button>

</div>

</template>


<style scoped>
</style>