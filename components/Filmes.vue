<script setup>

    // Pega os paramentros que foram passados
   // const params = useAttrs(); pega uma variavel apenas

    const params = defineProps(["filme", "alteraAlugado"]); // pega todo o objeto

</script>




<template>
<div class="conteudo ">
    <p>{{ params.filme.nome }}</p>
        <img src="https://m.media-amazon.com/images/I/61V96oRNd7L._AC_UF1000,1000_QL80_.jpg"/>
        <p>R$ {{ params.filme.preco }} </p>
       
    <button v-on:click="params.alteraAlugado( params.filme.id)" v-if="params.filme.alugado == false"class="btn">Alugar</button>
    <p v-if=" params.filme.alugado == true"> ALUGADO </p>
</div>
</template>

<style scoped>

   .conteudo{
    display: flex;
    flex-direction: column;
    width: 200px;
    text-align: center;
    background-color: black;
    padding: 15px;
    color: aliceblue;
    gap: 10px;
    border-radius: 10px;
   }

   .btn{
    background: red;
    border: none;
    padding: 10px;
    color: aliceblue;
    border-radius: 10px;

   }



</style>