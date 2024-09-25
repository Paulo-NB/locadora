<script setup>

    const categorias = [
        {nome: "Ação" },
        {nome: "Suspense" },
        {nome: "Terror" },
        {nome: "Dorama" },
        {nome: "Comédia" },
        {nome: "Romance" },
        {nome: "Documentário" },
        {nome: "Drama" },
    ]

</script>


<template>

    <h1>Categorias de Filmes</h1>


    <div v-for="categoria in categorias"> 
        <p>{{ categoria.nome }}</p>
    </div>

</template>