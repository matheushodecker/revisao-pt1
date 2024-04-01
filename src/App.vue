<script setup>
import { reactive, ref } from 'vue'

const titulo = ref('Titulo')
const mostrarResultado = ref(false)

const produto = reactive({
  nome: 'produto1',
  preco: 19.99,
  quantidade: 10,
  categorias: []
})

function formatarPreco(preco) {
  return `R$ ${preco.toFixed(2).replace('.', ',')}`
}
</script>

<template>
  <h1>{{ titulo }}</h1>
  <div class="container">
    <div class="formularios">
      <h2>formularios</h2>
      <input type="text" v-model="titulo">
      <form @submit.prevent="mostrarResultado = !mostrarResultado">
        <div class="row">
          <label for="">nome</label>
          <input type="text" v-model="produto.nome">
        </div>
        <div class="row">
          <label for="">preco</label>
          <input type="number" v-model="produto.preco">
        </div>
        <div class="row">
          <label for="">quantidade</label>
          <input type="number" v-model="produto.quantidade">
        </div>
        <button type="submit">mostrar</button>
      </form>
    </div>


    <div v-if="mostrarResultado" class="resultado">
      <h2>resultados</h2>

      <p>nome: {{ produto.nome }}</p>
      <p>preco: {{ formatarPreco(produto.preco) }}</p>
      <P>quantidade: {{ produto.quantidade }}</P>
      <p>categoria: {{ produto.categoria }}</p>
      <p>{{ mostrarResultado }}</p>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 1.5rem;
  width: 100vw;
}

.formularios,
.resultado {
  width: 45%;
  border-radius: 10px;
  padding: 10px;
}

.formularios {
  background-color: #c4c500;
}

.row {
  margin: 10px 20px;
  width: 70%;
  display: flex;
  justify-content: space-between;
}

.resultado {
  background-color: #c4c4c4;
}
</style>
