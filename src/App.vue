<script setup>
import { ref } from 'vue'
const nome = ref('')
const idade = ref('')
const email = ref('')

const mostrarPerfil = ref(false)

function salvarPerfil() {
  mostrarPerfil.value = true
}
</script>

<template>
  <div class="form">
    <main>
      <form action="">
        <h1>Formulaŕio:</h1>
        <label for="nome">Insira o seu nome:</label>
        <input v-model="nome" />
        <p></p>
        <label for="idade">Insira a sua idade:</label>
        <input type="number" v-model="idade" />
        <p></p>
        <label for="email">Insira o seu email:</label>
        <input v-model="email" />
      </form>
    </main>
  </div>
</template>
