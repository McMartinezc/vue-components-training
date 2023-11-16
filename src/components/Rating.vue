<script setup>
const props = defineProps(["rate"]);


</script>

<template>
    <div class="rating">
        <span v-for="index in 5">
            <span v-if="index <= rate">★</span>
            <span v-else>☆</span>
        </span>
    </div>
</template>

<style scoped></style>