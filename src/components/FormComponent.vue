<script setup>
import { ref } from 'vue'

const props = defineProps({
  dados: {
    type: Object,
    required: true
  },
  estados: {
    type: Array,
    required: true
  },
  hobbies: {
    type: Array,
    required: true
  },
  progUsuario: {
    type: Array,
    required: true
  }
})
const dadoscopy = ref({ ...props.dados })
</script>
<template>
  <form>
    <label for="dados.nome">Nome: </label>
    <input type="text" v-model="dadoscopy.nome" required />
    <hr />
    <label for="dados.email">E-mail: </label>
    <input type="email" v-model="dadoscopy.email" />
    <hr />
    <label for="dados.senha">Senha: </label>
    <input type="password" v-model="dadoscopy.senha" />
    <hr />
    <label for="dados.confSenha">Confirme sua senha: </label>
    <input type="password" v-model="dadoscopy.confSenha" />
    <hr />
    <label for="dados.endereco">Endereço: </label>
    <input type="string" v-model="dadoscopy.endereco" />
    <hr />
    <label for="dados.cidade">Cidade: </label>
    <input type="text" v-model="dadoscopy.cidade" />
    <hr />
    <label for="estados">Estado: </label>
    <select id="estado" v-model="dadoscopy.estado">
      <option selected disabled value="">Selecionar</option>
      <option v-for="opcao of props.estados" :key="opcao.sigla" :value="opcao.nomeEstados">
        {{ opcao.sigla }}
      </option>
    </select>
    <hr />
    <label for="hobbies"> Hobbies:</label>
    <template v-for="hobbie in props.hobbies" :key="hobbie.nome">
      <input v-model="dadoscopy.hobbie" :value="hobbie.nome" type="checkbox" />
      {{ hobbie.nome }}
    </template>
    <hr />
    <label for="progUsuario">Linguagens de programação:</label>
    <template v-for="linguagem in progUsuario" :key="linguagem.nome">
      <input v-model="dadoscopy.progUsuario" :value="linguagem.nome" type="checkbox" />
      {{ linguagem.nome }}
    </template>
 <hr />
        <label for="biografia" >Escreva uma breve biografia: </label>
        <input type="text" v-model="dadoscopy.biografia" minlength="10" maxlength="50" required/>
        <hr />
        <button type="submit" @click="confirmSenha">Mostrar resultado</button>
  </form>
</template>
