<script setup>
import { reactive, ref } from 'vue'

const titulo = ref('Titulo')
const mostrarResultado = ref(false)

const produto = reactive({
  nome: 'nome',
  email: 'email',
  senha: 'senha',
  Csenha: 'confirmacao senha',
  DataNascimento: 'data nascimento',
  endereco: 'endereco',
  cidade: 'cidade'
})

function formatarPreco(preco) {
  return `R$ ${preco.toFixed(2).replace('.', ',')}`
}


</script>

<template>
  <h1>{{ titulo }}</h1>
  <div class="container">
    <div v-if="!mostrarResultado" class="formularios">
      <h2>formularios</h2>
      <input type="text" v-model="titulo">
      <form @submit="mostrarResultado = !mostrarResultado">
        <div class="row">
         <label for="nome">nome</label>
         <input type="text" v-model="produto.nome">
        </div>
        <div class="row">
         <label for="email">email</label>
         <input type="text" v-model="produto.email">
        </div>
        <div class="row">
          <label for="senha">senha</label>
          <input type="text" v-model="produto.senha">
        </div>
        <div class="row">
          <label for="Csenha">confirmacao senha</label>
          <input type="text" v-model="produto.Csenha">
        </div>
        <div class="row">
          <label for="DataNascimento">data nascimento</label>
          <input type="date" v-model="produto.DataNascimento">
        </div>
        <div class="row">
          <label for="endereco">endereco</label>
          <input type="text" v-model="produto.endereco">
        </div>
        <div class="row">
          <label for="cidade">cidade</label>
          <input type="text" v-model="produto.cidade">
        </div>
        <div class="row">
          <label for="estado"></label>
          <label for="usuario.estado.value">estado</label>
      <br>
      <select name="estado" class="estado">
        <option value="AC">Acre</option>
        <option value="AL">Alagoas</option>
        <option value="AP">Amapá</option>
        <option value="AM">Amazonas</option>
        <option value="BA">Bahia</option>
        <option value="CE">Ceará</option>
        <option value="ES">Espírito Santo</option>
        <option value="GO">Goiás</option>
        <option value="MA">Maranhão</option>
        <option value="MT">Mato Grosso</option>
        <option value="AC">Mato Grosso do Sul</option>
        <option value="AC">Minas Gerais</option>
        <option value="AC">Pará</option>
        <option value="AC">Paraíba</option>
        <option value="AC">Paraná</option>
        <option value="AC">Pernambuco</option>
        <option value="AC">Piauí</option>
        <option value="AC">PI</option>
        <option value="AC">RJ</option>
        <option value="AC">RN</option>
        <option value="AC">RS</option>
        <option value="AC">RO</option>
        <option value="AC">RR</option>
        <option value="AC">SC</option>
        <option value="AC">SP</option>
        <option value="AC">SE</option>
        <option value="AC">TO</option>
      </select>
      <br>
        </div>
        <div class="row">
          <label for="Csenha">confirmacao senha</label>
          <input type="text" v-model="produto.Csenha">
        </div>
        <button type="submit">mostrar</button>
      </form>
    </div>


    <div v-else class="resultado">
      <h2>resultados</h2>

      <p>nome: {{ produto.nome }}</p>
      <p>email: {{ produto.email }}</p>
      <P>senha: {{ produto.senha }}</P>
      <p>Csenha: {{ produto.Csenha }}</p>
      <p>{{ mostrarResultado }}</p>
      <button @click="mostrarResultado = false">mostrar</button>
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
