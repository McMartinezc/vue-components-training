<script setup>
import { computed } from '@vue/reactivity';

const props = defineProps(['lastName', 'firstName', 'gender','height', 'birth', 'picture']);

const dateFormat = computed(()=>{
    const date = new Date(props.birth);
     return date.toDateString();
});

const heightFormat = computed (()=>{
    return (props.height / 100).toFixed(2);
});

</script>

<template>
    <div>
        <img :src="picture" :alt="firstName">
        <p><strong>First Name:</strong> {{ firstName }}</p>
        <p><strong>Last Name:</strong> {{ lastName }}</p>
        <p><strong>Gender:</strong> {{ gender }}</p>
        <p><strong>Height:</strong> {{ heightFormat }} m</p>
        <p><strong>Birth:</strong> {{ dateFormat }}</p>

    </div>
</template>

//scoped es que los estilos se aplican solo en este componente, encapsula el estilo en el componente
<style scoped>
div {
    border: 1px solid black;
    padding: 1rem;
    max-width: 500px;
}
</style>