<script setup>
import { computed } from '@vue/reactivity';
import { ref } from 'vue';

const counter = ref(0);
const colors= ref(['purple','blue','green','yellow','orange','red']);

const updateCounter = (click)=>{
    counter.value = counter.value + click;
}

const currentColor = computed(() => colors.value[counter.value]);

</script>


<template>

<div>
    <button :style="{backgroundColor: currentColor}" @click="updateCounter(1)">Likes {{ counter }}</button>
</div>

</template>


<style scoped>
</style>