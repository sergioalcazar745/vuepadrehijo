<template>
    <h1 style="color:blue">{{deporte}}</h1>
    <button @click="seleccionarFavorito()">Seleccionar favorito</button>
</template>

<script>
    export default {
        name: "PadreDeporte",
        props: ['deporte'],
        methods: {
            seleccionarFavorito(){
                this.$emit("mostrarFavorito", this.deporte)
            }
        },
        emits: ['mostrarFavorito']
    }
</script>

<style scoped>

</style>