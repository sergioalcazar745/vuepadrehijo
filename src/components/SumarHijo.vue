<template>
    <div>
        <h1 style="color: red">SumarHijo {{numero}}</h1>
        <button @click="sumarHijoPadre">Sumar</button>
    </div>
</template>

<script>
export default {
    name: 'SumarHijo',
    props: ['numero'],
    methods: {
        sumarHijoPadre(){
            this.$emit("sumarNumero", parseInt(this.numero))
        }
    },
    data() {
        return {
            
        };
    },
};
</script>

<style scoped>

</style>