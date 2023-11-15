<script setup>
import { computed } from 'vue';

const props = defineProps(['r', 'g', 'b']);

const getColorRGB = computed(() => {
    return `rgb( ${props.r}, ${props.g}, ${props.b})`;
});

const getColorHEX = () => {
    const toHex = (color) => {
        const hex = color.toString(16);
        return hex.length === 1 ? '0' + hex : hex;
    };

    const red = toHex(props.r);
    const green = toHex(props.g);
    const blue = toHex(props.b);

    return `#${red}${green}${blue}`;
};

</script>

<template>
    <div :style="{ backgroundColor: getColorRGB }">
        <p>{{ getColorRGB }}</p>
        <p>{{ getColorHEX() }}</p>
    </div>
</template>

<style scoped>
div {
    border: 2px solid black;
    margin-top: 10px;
}

p {
    text-align: center;
    color: whitesmoke;
}
</style>
