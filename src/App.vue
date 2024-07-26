<script setup>
import { ref } from 'vue'
import Form from './components/FormComponent.vue'
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

const estadosOpcoes = [
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

const resultado = ref(false)
function mostrarResultado() {
  resultado.value = true
}
const data = ref('')
function confirmSenha() {
  if (dados.value.confSenha == dados.value.senha) {
    mostrarResultado
    data.value =
      dados.value.nascimento.slice(8, 11) +
      '/' +
      dados.value.nascimento.slice(5, 7) +
      '/' +
      dados.value.nascimento.slice(0, 4)
  } else {
    alert('As senhas informadas não são iguais!')
  }
}

</script>

<template>
  <header>
    <h1>Formulário</h1>
  </header>
  <Form :dados="dados" :estados="estadosOpcoes" :hobbies="hobbiesUsuario" :progUsuario="progUsuario" />
  <ShowForm :resultado="resultado" :confirmSenha="confirmSenha"
  :mostrarResultado="mostrarResultado"/>
</template>

