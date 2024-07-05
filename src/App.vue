<script setup>
import { reactive, ref } from 'vue'

const mostrarResultado = ref(false)

const usuario = reactive({
  nome: 'Sarah',
  sobrenome: 'Jesus',
  email: 'sarahletjesus1908@gmail.com',
  senha: '',
  nascimento: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: [],
  lingProgs: '',
  biografia: ''
})
const hobbies = [
  {
    id: 1,
    nome: 'Esportes'
  },
  {
    id: 2,
    nome: 'Música'
  },
  {
    id: 3,
    nome: 'Artes'
  }
]
</script>

<template>
  
  <main>
    <div v-if="mostrarResultado" class="resultado">
      <h2>Dados do formulário</h2>
      <p>Nome: {{ usuario.nome }}</p>
      <p>Sobrenome: {{ usuario.sobrenome }}</p>
      <p>Email: {{ usuario.email }}</p>
      <p>Senha: {{ usuario.senha }}</p>
      <p>Nascimento: {{ usuario.nascimento }}</p>
      <p>Cidade: {{ usuario.cidade }}</p>
      <p>Estado: {{ usuario.estado }}</p>
      <p>Hobbies: {{ usuario.hobbies }}</p>
      <p>Linguagem de programação: {{ usuario.lingProgs }}</p>
      <p>Biografia: {{ usuario.biografia }}</p>
    </div>
    <div class="container" v-else>
      <h1>Meu Perfil</h1>
      <form>
        <label>Nome:</label>
        <input
          type="text"
          v-model="usuario.nome"
          autocomplete="on"
          style="width: 200px"
          maxlength="40"
          minlength="5"
          placeholder="Digite seu nome"
          required
        />
        <p></p>
        <label>Sobrenome:</label>
        <input
          type="text"
          v-model="usuario.sobrenome"
          autocomplete="on"
          style="width: 200px"
          maxlength="40"
          minlength="2"
          placeholder="Digite seu sobrenome"
          required
        />
        <p></p>
        <label>Email:</label>
        <input
          type="email"
          v-model="usuario.email"
          autocomplete="on"
          style="width: 200px"
          placeholder="Digite seu email"
          required
        />
        <p></p>
        <label>Senha:</label>
        <input
          type="password"
          v-model="usuario.senha"
          autocomplete="on"
          style="width: 200px"
          placeholder="Digite a senha"
          required
        />
        <p></p>
        <label>Data de nascimento:</label>
        <input
          type="date"
          v-model="usuario.nascimento"
          autocomplete="on"
          style="width: 200px"
          placeholder="Indique sua data de nascimento"
          required
        />
        <p></p>
        <label>Endereço:</label>
        <input
          type="text"
          v-model="usuario.endereco"
          autocomplete="on"
          style="width: 200px"
          maxlength="40"
          minlength="5"
          placeholder="Digite o seu endereço"
          required
        />
        <p></p>
        <label>Cidade:</label>
        <input
          type="text"
          v-model="usuario.cidade"
          autocomplete="on"
          style="width: 200px"
          maxlength="40"
          minlength="5"
          placeholder="Digite sua cidade"
          required
        />
        <p></p>
        <label for="estado">Estado:</label>
        <select v-model="usuario.estado">
          <option value="AC">Acre</option>
          <option value="AL">Alagoas</option>
          <option value="AP">Amapá</option>
          <option value="AM">Amazônia</option>
          <option value="BA">Bahia</option>
          <option value="CE">Ceará</option>
          <option value="DF">Distrito Federal</option>
          <option value="ES">Espirito Santo</option>
          <option value="GO">Goiás</option>
          <option value="MA">Maranhão</option>
          <option value="MT">Mato Grosso</option>
          <option value="MS">Mato Grosso do Sul</option>
          <option value="MG">Minas Gerais</option>
          <option value="PA">Pará</option>
          <option value="PB">Paraiba</option>
          <option value="PR">Paraná</option>
          <option value="PE">Pernambuco</option>
          <option value="PI">Piauí</option>
          <option value="RJ">Rio de Janeiro</option>
          <option value="RN">Rio Grande do Norte</option>
          <option value="RS">Rio Grande do Sul</option>
          <option value="RO">Rondonia</option>
          <option value="RR">Roraima</option>
          <option value="SC">Santa Catarina</option>
          <option value="SP">São Paulo</option>
          <option value="SE">Sergipe</option>
          <option value="TO">Tocantins</option>
        </select>
        <p></p>
        <label>Hobbies:</label>
        <div class="items-checkbox">
          <template v-for="hobbie in hobbies" :key="hobbie.id">
            <input type="checkbox" :value="hobbie.nome" v-model="usuario.hobbies" /> {{ hobbie.nome }}
          </template>
        </div>
        <p></p>
        <label for="lingProgs">Linguagem de programação preferida:</label>
        <select v-model="usuario.lingProgs">
          <option value="C">C</option>
          <option value="C++">C++</option>
          <option value="Python">Python</option>
          <option value="Java">Java</option>
        </select>
        <p></p>
        <label>Biografia:</label>
        <input
          type="text"
          v-model="usuario.biografia"
          autocomplete="on"
          style="width: 200px"
          maxlength="40"
          minlength="5"
          placeholder="Escreva sua biografia:"
        />
        <button @click="mostrarResultado = !mostrarResultado">Mostrar</button>
      </form>
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: center;
  padding: 20px;
  background-color: bisque;
  min-height: 100vh;
}

.container {
  width: 350px;
  background-color: rgb(162, 100, 219); 
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  color: rgb(54, 0, 99);
  font-family: 'Arial', sans-serif;
}

label {
  display: block;
  margin: 10px 0 5px;
  color: rgb(54, 0, 99);
  font-weight: bold;
  font-family: 'Arial', sans-serif;
}

input, select {
  padding: 8px;
  border-radius: 20px;
  border: 1px solid;
  margin-bottom: 15px;
  font-family: 'Arial', sans-serif;
}

.items-checkbox {
  display: flex;
}

.items-checkbox input {
  margin-right: 5px;
}

button {
  display: block;
  padding: 15px 30px;
  color: rgb(255, 255, 255);
  border-radius: 20px;
  background-color: rgb(119, 47, 192);
}

button:hover {
  background-color: rgb(54, 0, 99);
}

.resultado {
  background-color: rgb(157, 122, 190);
  padding: 20px;
  border-radius: 10px;
}

.resultado h2 {
  color: rgb(54, 0, 99);
  font-family: 'Arial', sans-serif;
}

.resultado p {
  font-family: 'Arial', sans-serif;
  margin-bottom: 10px;
}
</style>
