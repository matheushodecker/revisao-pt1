<script setup>
import { ref } from 'vue'

const titulo = ref('Titulo')

</script>

<template>
  <h1>{{ titulo }}</h1>
  <div class="container">
    <div class="formularios">
      <h2>formularios</h2>
      <input type="text" v-model="titulo">
    </div>
    <div class="resultado">
      <h2>resultados</h2>
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

.resultado {
  background-color: #c4c4c4;
}
</style>
