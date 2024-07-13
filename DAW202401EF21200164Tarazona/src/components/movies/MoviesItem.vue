<template>
    <q-card class="movies-card">
        <q-card-section>
            <q-img :src="movies.imageUrl" alt="Listado de Programas de TV"/>
        </q-card-section>
        <q-card-section>
                <q-card-title>{{movies.descripcion}}</q-card-title>
                <div class="text-h6 font-weight-bold">
                    {{ movies.price }}
                </div>
                <div class="text-center">
                    <q-btn color="primary" icon="add_shopping_cart" 
                    label="Agregar"></q-btn>
                </div>
        </q-card-section>
    </q-card>
    
    </template>
    
    <style>
        .movies-card{
            width: 300px;
        }
        .movies-card q-card-section {
            height: 100px;
            overflow: hidden;
        }
    </style>
    
    <script>
    
    export default{
        name: "moviesItem",
        props: {
            movies:{
                type: Object,
                required: true
            }
        }
    }
    
    </script>