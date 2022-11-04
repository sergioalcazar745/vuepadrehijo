<template>
    <div>
        <h1>HijoComic</h1>
        <table>
            <thead>
                <th>Titulo</th>
                <th>Imagen</th>
                <th>Descripcion</th>
                <th>Año</th>
                <th>Favorito</th>
                <th>Accion</th>
            </thead>
            <tbody>
                <tr>
                    <td :class="{rojo: comic.year > 2000, verde: comic.year <= 2000}">{{comic.titulo}}</td>
                    <td>{{comic.descripcion}}</td>
                    <td>{{comic.year}}</td>
                    <td><img :src="comic.imagen"/></td>
                    <td><button @click="this.$emit('mostrarFavorito', comic)">Añadir</button></td>
                    <td><button @click="this.$emit('eliminarComic', index)">Eliminar</button></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: 'HijoComic',
    props: ['comic', 'index'],
    data() {
        return {
            
        };
    },
};
</script>

<style scoped>
@import url("./../assets/css/estilocomic.css");
</style>