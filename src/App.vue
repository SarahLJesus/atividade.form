<script setup>
import { ref } from 'vue'
const user = ref({
  name: 'Sarah Letícia',
  surname: 'Jesus',
  email: 'sarahletjesus1908@gmail.com',
})
const mostrarPerfil = ref(false)

function salvarPerfil() {
  mostrarPerfil.value = true
}
</script>

<template>
  <div class="container">
    <main>
      <h1>Meu Perfil</h1>
        <transition name="form" mode="out-in">
        <section v-if="mostrarPerfil">
        <button class="btn btn-info" @click="mostrarPerfil = false">Esconder</button>
        </section>
        <form v-else class="row g-3 was-validated" @submit.prevent="salvarPerfil()" validate>
          <div class="col-md-4">
            <label for="nameField" class="form-label">Nome</label>
            <input type="text" class="form-control" id="nameField" v-model="user.name" required />
            <div class="invalid-feedback">Nome obrigatório</div>
          </div>
          <div class="col-md-4">
            <label for="surnameField" class="form-label">Sobrenome</label>
            <input
              type="text"
              class="form-control"
              id="surnameField"
              v-model="user.surname"
              required
            />
            <div class="invalid-feedback">Sobrenome obrigatório</div>
          </div>
          </form>
        </transition>
    </main>
  </div>
</template>
