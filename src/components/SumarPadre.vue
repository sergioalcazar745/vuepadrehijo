<template>
    <div>
        <h1 style="color:blue">SumarPadre</h1>
        <h1 style="color:green" v-if="suma > 0">La suma es: {{suma}}</h1>
        <button @click="getArrayRandom">Crear hijo</button>
        <ul>
            <li v-for="num in numeros" :key="num">
                <SumarHijo :numero="num" v-on:sumarNumero="sumarNumero"/>
            </li>
        </ul>
    </div>
</template>

<!------------------------------------ SCRIPT ------------------------------------>

<script>
import SumarHijo from './SumarHijo.vue'
export default {
    name: 'SumarPadre',

    components:{
        SumarHijo
    },

    methods: {
        sumarNumero(numero){
            this.suma += numero
        },

        getRandom(){
            return Math.floor(Math.random() * 100);
        },

        getArrayRandom(){
            this.numeros.push(this.getRandom())
        }
    },

    mounted() {
        //this.getArrayRandom()
    },

    data() {
        return {
            numeros: [],
            suma: 0
        };
    },
};
</script>

<!------------------------------------ STYLES ------------------------------------>

<style scoped>

</style>
