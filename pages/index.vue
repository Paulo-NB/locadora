<script setup>


    const filmes = reactive( [
        {
          id:0,   
          nome:  "Batman: Begin o começo sssdddddd",
          preco:"20,00",
          alugado: false,
        },
        {
          id:1,   
          nome:"Batman: O Cavaleiro das Trevas",
          preco: "20,00",
          alugado: false,
        },
        {
          id:2,   
          nome:"Batman: O Cavaleiro das Trevas Ressurge",
          preco: "20,00",
          alugado: true,
        },
    ])

    function alteraAlugado(id){
      filmes[id].alugado = true;
    }


</script>

<template>

    <Cabecalho/>

    <hr/>
    <p><strong> Filmes Recomendados </strong></p>


    <div class="conteudo btn">
        <Filmes v-for="filme in filmes" v-bind:filme="filme" v-bind:alteraAlugado="alteraAlugado" />
    </div>

</template>

<style>

.conteudo{

  display: flex;
  gap: 20px;
  

}




</style>
