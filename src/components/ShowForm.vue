<script setup>

const props = defineProps({
  dados: {
    type: Object,
  },
  resultado: {
type: Boolean
  }
})
</script>
<template>

 <button type="submit" @click="confirmSenha">Mostrar resultado</button>
    <section v-if="resultado">
      <div>
        <p>Nome: {{ dados.nome }}</p>
        <hr />
        <p>E-mail: {{ props.dados.email }}</p>
        <hr />
        <p>Senha: {{ props.dados.senha }}</p>
        <hr />
        <p>Data de nascimento: {{ data }}</p>
        <hr />
        <p>Endereço: {{ props.dados.endereco }}</p>
        <hr />
        <p>Cidade {{ props.dados.cidade }}</p>
        <hr />
        <p>Estado: {{ props.dados.estado }}</p>
        <hr />
        <p>Hobbies: {{ props.dados.hobbie }}</p>
        <hr />
        <p>Linguagens de programação: {{ props.dados.linguagensProg}}</p>
        <hr />
        <p>Biografia: {{ props.dados.biografia }}</p>
      </div>
    </section>
</template>