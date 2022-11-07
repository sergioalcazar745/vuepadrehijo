<template>
  <div>
    <h1>Número doble parámetros</h1>
    <h2 v-if="mensaje">{{ mensaje }}</h2>
    <div v-else-if="!isNaN(numero)">
        <h2>El numero recibido es: {{ numero }}</h2>
        <h2>El doble es {{ doble }}</h2>
    </div>
    <button @click="redirectToHome">Go to Home</button>
  </div>
</template>

<script>
export default {
    name: 'NumeroDoble',

    methods: {
        redirectToHome(){
            this.$router.push("/");
        },

        getParams(){
            this.mensaje = null;
            this.numero = parseInt(this.$route.params.numero);
            this.doble = this.numero * 2;   
        }
    },

    watch: {
        '$route.params.numero'(nextVal, oldVal){
            if(nextVal != oldVal){
                this.getParams()
            }
        }
    },

    mounted() {
        if(this.$route.params.numero == ""){
            this.mensaje = "No tenemos parametros";
        }else{
            this.getParams();  
        }  
    },

    data() {
        return {
            numero: 0,
            doble: 0,
            mensaje: null
        };
    },
};
</script>

<style scoped>
</style>