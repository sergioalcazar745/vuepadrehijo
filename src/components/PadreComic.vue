<template>
    <div>
        <h1>Padre comic</h1>
        <h2 v-if="comicFavorito != null">Favorito: {{comicFavorito}}</h2>
        <form v-on:submit.prevent="crearComic">
            <label>Título: </label>
            <input type="text" v-model="comicForm.titulo"/><br/>
            <label>URL imagen</label>
            <input type="text" v-model="comicForm.imagen"/><br/>
            <label>Descripcion</label>
            <input type="text" v-model="comicForm.descripcion"/><br/>
            <label>Año</label>
            <input type="number" v-model="comicForm.year"/><br/><br/>
            <button>Nuevo comic</button>
        </form>
        <ul>
            <li id="comic" v-for="(comic, index) in comics" :key="comic">
                <HijoComic :comic="comic" :index="index" v-on:mostrarFavorito="mostrarFavorito" v-on:eliminarComic="eliminarComic"/>
            </li>
        </ul>
    </div>
</template>

<script>
import HijoComic from './HijoComic.vue';
export default {
    name: 'PadreComic',

    methods: {

        crearComic() {
            var comicJSON = {
                titulo: this.comicForm.titulo,
                imagen: this.comicForm.imagen,
                descripcion: this.comicForm.descripcion,
                year: this.comicForm.year
            }
            this.comics.push(comicJSON)
        },

        mostrarFavorito(comicHijo){
            this.comicFavorito = comicHijo
        },

        eliminarComic(index){
            this.comics.splice(index, 1)
        }
    },

    components:{
        HijoComic
    },

    data() {
        return {

            comics: [
                {
                titulo: "Spiderman",
                imagen:
                    "https://3.bp.blogspot.com/-i70Zu_LAHwI/T290xxduu-I/AAAAAAAALq8/8bXDrdvW50o/s1600/spiderman1.jpg",
                descripcion: "Hombre araña"
                , year: 1997
                },
                {
                titulo: "Wolverine",
                imagen:
                    "https://images-na.ssl-images-amazon.com/images/I/51c1Q1IdUBL._SX259_BO1,204,203,200_.jpg",
                descripcion: "Lobezno"
                , year: 2003
                },
                {
                titulo: "Guardianes de la Galaxia",
                imagen:
                    "https://cdn.normacomics.com/media/catalog/product/cache/1/thumbnail/9df78eab33525d08d6e5fb8d27136e95/g/u/guardianes_galaxia_guadianes_infinito.jpg",
                descripcion: "Yo soy Groot"
                , year: 2006
                },
                {
                titulo: "Avengers",
                imagen:
                    "https://d26lpennugtm8s.cloudfront.net/stores/057/977/products/ma_avengers_01_01-891178138c020318f315132687055371-640-0.jpg",
                descripcion: "Los Vengadores"
                , year: 1993
                },
                {
                titulo: "Spawn",
                imagen:
                    "https://i.pinimg.com/originals/e1/d8/ff/e1d8ff4aeab5e567798635008fe98ee1.png",
                descripcion: "Al Simmons"
                , year: 2000
                },
                {
                titulo: "Batman",
                imagen:
                    "https://www.comicverso.com/wp-content/uploads/2020/06/The-Killing-Joke-657x1024.jpg",
                descripcion: "Murcielago"
                , year: 2001
                }
            ],

            comicForm: {
                titulo: "",
                imagem: "",
                descripcion: "",
                year: ""
            },

            comicFavorito: null

        };
    },
};
</script>

<style scoped>

</style>