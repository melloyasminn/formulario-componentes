<script setup>
import { reactive, ref } from 'vue'

const emit = defineEmits(['enviar'])

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

const dadosForm = reactive({
  nome: '',
  email: '',
  senha: '',
  data: '',
  confirmSenha: '',
  estado: '',
  cidade: "",
  biografia: '',
  progUsuario: [],
  hobbies: [],
  endereco: ''
})


function salvar(){

  emit('enviar', dadosForm)
}

</script>
<template>
  <form @submit.prevent="salvar">
    <label for="dados.nome">Nome: </label>
    <input type="text" v-model="dadosForm.nome" required />
    <hr />
    <label for="dados.email">E-mail: </label>
    <input type="email" v-model="dadosForm.email" />
    <hr />
    <label for="dados.nascimento">Nascimento:</label>
    <input type="date" v-model="dadosForm.data">
    <hr />
    <label for="dados.senha">Senha: </label>
    <input type="password" v-model="dadosForm.senha" />
    <hr />
    <label for="dados.confSenha">Confirme sua senha: </label>
    <input type="password" v-model="dadosForm.confirmSenha" />
    <hr />
    <label for="dados.endereco">Endereço: </label>
    <input type="string" v-model="dadosForm.endereco" />
    <hr />
    <label for="dados.cidade">Cidade: </label>
    <input type="text" v-model="dadosForm.cidade" />
    <hr />
    <label for="estados">Estado: </label>
    <select id="estado" v-model="dadosForm.estado">
      <option selected disabled value="">Selecionar</option>
      <option v-for="opcao of props.estados" :key="opcao.sigla" :value="opcao.nomeEstados">
        {{ opcao.sigla }}
      </option>
    </select>
    <hr />
    <label for="hobbies"> Hobbies:</label>
    <template v-for="hobbie in props.hobbies" :key="hobbie.nome">
      <input v-model="dadosForm.hobbies" :value="hobbie.nome" type="checkbox" />
      {{ hobbie.nome }}
    </template>
    <hr />
    <label for="progUsuario">Linguagens de programação:</label>
    <template v-for="linguagem in progUsuario" :key="linguagem.nome">
      <input v-model="dadosForm.progUsuario" :value="linguagem.nome" type="checkbox" />
      {{ linguagem.nome }}
    </template>
 <hr />
        <label for="biografia" >Escreva uma breve biografia: </label>
        <input type="text" v-model="dadosForm.biografia" minlength="10" maxlength="50" required/>
        <hr />
        <button type="submit" @click="confirmSenha">Mostrar resultado</button>
  </form>
</template>
