<script setup>
defineProps({
  dados: {
    type: Object,
    required: true
  },
  estados:{
    type: Array,
    required: true
  },
  hobbiesUsuario:{
    type: Array,
    required: true
  },
  progUsuario:{
    type: Array,
    required: true
  }
})
</script>
<template>
  <label for="dados.nome">Nome: </label>
  <input type="text" v-model="dados.nome" />
  <hr>
  <label for="dados.email">E-mail: </label>
  <input type="email" v-model="dados.email" />
  <hr>
  <label for="dados.senha">Senha: </label>
  <input type="password" v-model="dados.senha" />
  <hr>
  <label for="dados.confSenha">Confirme sua senha: </label>
  <input type="password" v-model="dados.confSenha" />
  <hr>
  <label for="dados.endereco">Endereço: </label>
  <input type="string" v-model="dados.endereco" />
  <hr>
  <label for="dados.cidade">Cidade: </label>
  <input type="text" v-model="dados.cidade" />
  <hr>
</template>
