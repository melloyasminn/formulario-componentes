<script setup>
import { ref } from 'vue'
import Form from './components/Form.vue'
import ShowForm from './components/ShowForm.vue'
const dados = ref({
  nome: '',
  email: '',
  senha: '',
  confSenha: '',
  nascimento: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbie: [],
  linguagensProg: [],
  biografia: ''
})

const hobbiesUsuario = [
  { nome: 'Dança' },
  { nome: 'Instrumentos musicais' },
  { nome: 'Esportes' },
  { nome: 'Culinária' }
]

const progUsuario = [
  { nome: 'JavaScript' },
  { nome: 'Java' },
  { nome: 'Python' },
  { nome: 'PHP' },
  { nome: 'C++' }
]

const estados = [
  { sigla: 'AC', nomeEstados: 'Acre' },
  { sigla: 'AL', nomeEstados: 'Alagoas' },
  { sigla: 'AP', nomeEstados: 'Amapá' },
  { sigla: 'AM', nomeEstados: 'Amazonas' },
  { sigla: 'BA', nomeEstados: 'Bahia' },
  { sigla: 'CE', nomeEstados: 'Ceará' },
  { sigla: 'DF', nomeEstados: 'Distrito Federal' },
  { sigla: 'ES', nomeEstados: 'Espírito Santo' },
  { sigla: 'GO', nomeEstados: 'Goiás' },
  { sigla: 'MA', nomeEstados: 'Maranhão' },
  { sigla: 'MT', nomeEstados: 'Mato Grosso' },
  { sigla: 'MS', nomeEstados: 'Mato Grosso do Sul' },
  { sigla: 'MG', nomeEstados: 'Minas Gerais' },
  { sigla: 'PA', nomeEstados: 'Pará' },
  { sigla: 'PB', nomeEstados: 'Paraíba' },
  { sigla: 'PR', nomeEstados: 'Paraná' },
  { sigla: 'PE', nomeEstados: 'Pernambuco' },
  { sigla: 'PI', nomeEstados: 'Piauí' },
  { sigla: 'RJ', nomeEstados: 'Rio de Janeiro' },
  { sigla: 'RN', nomeEstados: 'Rio Grande do Norte' },
  { sigla: 'RS', nomeEstados: 'Rio Grande do Sul' },
  { sigla: 'RO', nomeEstados: 'Rondônia' },
  { sigla: 'RR', nomeEstados: 'Roraima' },
  { sigla: 'SC', nomeEstados: 'Santa Catarina' },
  { sigla: 'SP', nomeEstados: 'São Paulo' },
  { sigla: 'SE', nomeEstados: 'Sergipe' },
  { sigla: 'TO', nomeEstados: 'Tocantins' }
]

</script>

<template>
  <header>
      <h1>Formulário</h1>
  </header>

  <Form :dados="dados" />
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');

h1 {
  font-family: 'Bebas Neue', sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 50%;
  margin: 0;
  text-align: left;
  padding: 0;
}
header{
padding: 0;
  background: #a1a1a1;
}
</style>
