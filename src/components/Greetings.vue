<script setup>
const props = defineProps(['lang']);



</script>

<template>
    <div>
        <!--slot sirve para puedes tener áreas predefinidas donde se espera que el contenido sea insertado desde fuera del componente-->
        <p v-if='lang === "de"'>Hallo! <slot></slot>
        </p>
        <p v-else-if='lang === "fr"'>Bonjour! <slot></slot>
        </p>
        <p v-else-if='lang === "es"'>Hola! <slot></slot>
        </p>
        <p v-else>Hello! <slot></slot>
        </p>
    </div>
</template>

<style scoped></style>