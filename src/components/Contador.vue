<template>
 <div class="contador">
     <h3>Porcentagem de vagas preenchidas</h3>
     {{ porcentagem }}%
     <div class="botoes">
        <button type="button" @click="quantidadePessoasCadastradas++" :disabled="habilitarBotao">Cadastrar Pessoa</button>
        <button type="button" @click="quantidadePessoasCadastradas--" :disabled="!habilitarBotao">Cancelar Cadastro</button>         
     </div>
 </div>
</template>

<script>
export default {
    data() {
        return {
            quantidadePessoasCadastradas: 0,
            habilitarBotao: false
        }
    },
    watch: {
        quantidadePessoasCadastradas(novoValor) {            
            if (novoValor === this.quantidadeVagas) {
                this.habilitarBotao = !this.habilitarBotao
                this.encerrarVagas()
            }
        }
    },
    computed: {
        porcentagem() {
            return (this.quantidadePessoasCadastradas * 100/this.quantidadeVagas).toFixed(2)
        }
    },
    props: {
        quantidadeVagas: {
            type:Number,
            require:true
        }
    },
    methods: {
        encerrarVagas() {
            this.$emit('vagasEncerradas')
        }
    }
}
</script>
<style>

</style>