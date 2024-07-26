<script setup>

const props = defineProps({
  dados: {
    type: Object,
  },
  resultado: {
type: Boolean
  }
})

function formatData(data) {
  return data.slice(8, 11) +
    '/' +
    data.slice(5, 7) +
    '/' +
    data.slice(0, 4)
}

</script>
<template>


    <section v-if="resultado">
      <div>
        <p>Nome: {{ props.dados.nome }}</p>
        <hr />
        <p>E-mail: {{ props.dados.email }}</p>
        <hr />
        <p>Senha: {{ props.dados.senha }}</p>
        <hr />
        <p>Data de nascimento: {{ formatData(props.dados.data) }}</p>
        <hr />
        <p>Endereço: {{ props.dados.endereco }}</p>
        <hr />
        <p>Cidade {{ props.dados.cidade }}</p>
        <hr />
        <p>Estado: {{ props.dados.estado }}</p>
        <hr />
        <p>Hobbies: {{ props.dados.hobbies }}</p>
        <hr />
        <p>Linguagens de programação: {{ props.dados.progUsuario}}</p>
        <hr />
        <p>Biografia: {{ props.dados.biografia }}</p>
      </div>
    </section>
</template>