<script setup>
import { ref } from 'vue';

const props = defineProps(['images'])
const index =ref(0);

const goLeft = ()=>{
    index.value--;

    if(index.value < 0){
        index.value = props.images.length -1;
    }
}

const goRight = ()=>{
    index.value++;

    if(index.value == props.images.length){
        index.value=0;
    }
}

</script>

<template>
  <div>
        <button v-on:click="goLeft">Left</button>
        <img v-bind:src="images[index]" alt="">
        <button @click="goRight">Right</button>
    </div>
</template>

<style scoped>
</style>