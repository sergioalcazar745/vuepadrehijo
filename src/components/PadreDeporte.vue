<template>
    <h1 style="color:red">Padre deporte</h1>
    <h1 v-if="favorito != ''">Favorito {{favorito}}</h1>
    <ul>
        <li v-for="depor in deportes" :key="depor">
            <HijoDeporte :deporte="depor" v-on:mostrarFavorito="mostrarFavorito"/>
        </li>
    </ul>
    
</template>

<script>
    import HijoDeporte from  './HijoDeporte.vue'
    export default {
        name: "PadreDeporte",
        components: {
            HijoDeporte
        },
        data() {
            return{
                deportes: ["Surf", "Futbol", "Baloncesto", "Hockey", "Paddle"],
                favorito: ""
            }
        },
        methods: {
            mostrarFavorito(nombre){
                this.favorito = nombre
            }
        }
    }
</script>

<style scoped>

</style>