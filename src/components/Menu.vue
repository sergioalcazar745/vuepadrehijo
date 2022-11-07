<template>
    <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/deportes">Deportes</router-link></li>
        <li><router-link to="/comics">Comics</router-link></li>
        <li><router-link to="/doble/10">NumeroDoble</router-link></li>
        <li><router-link to="/doble">NumeroDoble sin numero</router-link></li>
    </ul>
</template>

<script>
export default {
    name: 'MenuComponent',
    data() {
        return {
            
        };
    },
};
</script>

<style scoped>
    ul li{
        display: inline;
        padding: 15px;        
    }
    
    ul li a {
        text-decoration: none;
        font-size: 18px;
    }
</style>