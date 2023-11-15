<script setup>

const props = defineProps(['min', 'max']);

const getRandom = ()=>{
    return Math.floor(Math.random() * (props.max - props.min + 1)+ props.min);
}

</script>

<template>
<div>
    <p>Random value between {{ min }} and {{ max }} => <span class="randomNumber"><strong>{{ getRandom() }}</strong></span></p>
</div>
</template>


<style scoped>
.randomNumber{
    color:brown;
}
</style>