<script setup>
import { reactive, ref } from 'vue'

const mostrarResultado = ref(false)

const produto = reactive({
  nome: 'nome',
  email: 'email',
  senha: 'senha',
  Csenha: 'confirmacao senha',
  DataNascimento: 'data nascimento',
  endereco: 'endereco',
  cidade: 'cidade',
  estado: 'estado',
  hobbies: 'hobbies',
  linguagem: 'linguagem programação',
  biografia: 'biografia',

})
</script>

<template>
  <div class="container">
    <div v-if="!mostrarResultado" class="formularios">
      <h1>formularios</h1>
      
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
          <label for="estado">estado</label>
          <select name="estado" class="estado" v-model="produto.estado">
            <option value="AC">Acre</option>
            <option value="AL">Alagoas</option>
            <option value="AP">Amapá</option>
            <option value="AM">Amazonas</option>
            <option value="BA">Bahia</option>
            <option value="CE">Ceará</option>
            <option value="DF">Distrito federal</option>
            <option value="ES">Espírito Santo</option>
            <option value="GO">Goiás</option>
            <option value="MA">Maranhão</option>
            <option value="MT">Mato Grosso</option>
            <option value="MS">Mato Grosso do Sul</option>
            <option value="MG">Minas Gerais</option>
            <option value="PA">Pará</option>
            <option value="PB">Paraíba</option>
            <option value="PR">Paraná</option>
            <option value="PE">Pernambuco</option>
            <option value="PI">Piauí</option>
            <option value="RJ">Rio de Janeiro</option>
            <option value="RN">Rio Grande do Norte</option>
            <option value="RS">Rio Grande do Sul</option>
            <option value="RO">Rondonia</option>
            <option value="RR">Roraima</option>
            <option value="SC">Santa Catarina</option>
            <option value="SP">São paulo</option>
            <option value="SE">Sergipe</option>
            <option value="TO">Tocantins</option>
          </select>
        </div>
        <div class="row">
          <label for="hobbies">hobbies</label>
          <input type="text" v-model="produto.hobbies">
        </div>
        <div class="row">
          <label for="linguagem">linguagem de programação</label>
          <input type="text" v-model="produto.linguagem">
        </div>
        <div class="row">
          <label for="biografia">biografia</label>
          <input type="text" v-model="produto.biografia">
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
      <p>Data: {{ produto.DataNascimento }}</p>
      <p>endereco: {{ produto.endereco }}</p>
      <p>cidade: {{ produto.cidade }}</p>
      <p>estado: {{ produto.estado }}</p>
      <p>hobbies: {{ produto.hobbies }}</p>
      <p>linguagem: {{ produto.linguagem }}</p>
      <p>biografia: {{ produto.biografia }}</p>
      <p>{{ mostrarResultado }}</p>
      <button @click="mostrarResultado = false">mostrar</button>
    </div>
  </div>
</template>

<style scoped>
template{
  background-color: black;
}
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 1.5rem;
  width: 100vw;
  padding: 25vh 5vh;
}

.formularios,
.resultado {
  width: 45%;
  border-radius: 10px;
  padding: 25px;
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
