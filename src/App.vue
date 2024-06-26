<script setup>
import { ref } from 'vue'

</script>

<template>
  <div class="container">
    <main>
      <h1>Meu Perfil</h1>
      <p>Nome:</p>
      <input
        type="text"
        v-model="nome"
        autocomplete="on"
        style="width: 200px"
        v-model.trim="nome"
        maxlength="40"
        minlength="5"
        placeholder="Digite seu nome"
        required 
      />
      <p>Sobrenome:</p>
      <input
        type="text"
        v-model="sobrenome"
        autocomplete="on"
        style="width: 200px"
        maxlength="40"
        minlength="2"
        placeholder="Digite seu sobrenome"
        required 
      />
      <p>Email:</p>
      <input
        type="email"
        v-model="email"
        autocomplete="on"
        style="width: 200px"
        v-model.trim="email"
        placeholder="Digite seu email"
        required 
      />
      <p>Senha:</p>
      <input
        type="password"
        v-model="senha"
        autocomplete="on"
        style="width: 200px"
        placeholder="Digite a senha"
        required 
      />
      <p>Data de nascimento:</p>
      <input
        type="date"
        v-model="nascimento"
        autocomplete="on"
        style="width: 200px"
        placeholder="Indique sua data de nascimento"
        required 
        />
        <p>Cidade:</p>
        <input
        type="text"
        v-model="cidade"
        autocomplete="on"
        style="width: 200px"
        v-model.trim="cidade"
        maxlength="40"
        minlength="5"
        placeholder="Digite sua cidade"
        required 
      />

    </main>
  </div>
</template>
<style scoped>
.container {
  margin: 100px 600px;
  background-color: rgb(195, 131, 255);
  border-radius: 10px;
}

</style>
