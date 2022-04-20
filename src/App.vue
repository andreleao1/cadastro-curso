<template>
  <div class="componente-principal">
    <h1>Cadastro de curso</h1>
    <p>Entre com a quantidade de vagas:</p>
    <input type="number" v-model="quantidadeVagas"/>
    <Contador :quantidadeVagas="quantidadeVagas" @vagasEncerradas="encerrarVagas"/>
  </div>
</template>

<script>
import Contador from './components/Contador.vue'

export default {
  name: 'App',
  data() {
    return {
      quantidadeVagas: 0
    }
  },
  components: {
    Contador
  },
  methods:{
    encerrarVagas() {
      alert('Vagas encerradas!')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
