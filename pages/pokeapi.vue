<script setup>


    import axios from "axios";

    let dados = ref();
    let digitado = ref("");
    

    async function buscaTodos(){
        let resposta = await axios.get("https://pokeapi.co/api/v2/pokemon/blastoise")
        console.log( resposta );

        dados.value = resposta.data;
        
    }

    async function pesquisar(){
        let resposta = await axios.get("https://pokeapi.co/api/v2/pokemon/"+digitado.value)
        console.log( resposta );

        dados.value = resposta.data;
    }

    onMounted(()=>{

        buscaTodos();
        

    })
</script>



<template>
    <h1>
         Consulta na API do Pokémon  
    </h1>

    
    <input v-model="digitado" placeholder="Digite o nome de um Pokémon" size="25px"/>
    <button v-on:click="pesquisar()" > Pesquisar </button>


    <div v-if=" dados !=null ">
        <p>Dados do Pokémon: {{ dados.name }}</p>

            <p> o id é {{ dados.id }}</p>

                <p> habilidade: {{ dados.abilities[0].ability.name }}  </p>

                <p v-if="dados.abilities[1]"> Segunda habilidade: {{ dados.abilities[1].ability.name }}  </p>

            <p> Altura: {{ dados.height}} Metros </p>

        <img v-bind:src="dados.sprites.front_default" width="150px"/>
    </div>


</template>