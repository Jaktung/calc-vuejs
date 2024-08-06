<script setup>
    import { reactive } from 'vue';

    const estado = reactive({
        primeiroNumero: '',
        segundoNumero: '',
        operacoes: {
            adicao: (a, b) => a + b,
            subtracao: (a, b) => a - b,
            multiplicacao: (a, b) => a * b,
            divisao: (a, b) => (b !== 0 ? a / b : 'Divisao por zero'),
        },
        resultado: 0,
    });

    const calculaResultado = () => {
        const {primeiroNumero, segundoNumero, operacaoMatematica} = estado;
        estado.resultado = estado.operacoes[operacaoMatematica](parseFloat(primeiroNumero), parseFloat(segundoNumero));
    };
</script>

<template>
    <div class="container rounded">
      <h1>Calculadora</h1>
      <form>
        <div class="row mb-3">
          <input placeholder="Digite um número" type="number" v-model="estado.primeiroNumero" @input="calculaResultado" required class="form-control mb-3">
          <input placeholder="Digite um número" type="number" v-model="estado.segundoNumero" @input="calculaResultado" required class="form-control mb-3">
          <select v-model="estado.operacaoMatematica" @change="calculaResultado" class="mb-4">
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
          </select>
          <button type="button" class="btn btn-primary">Calcular</button>
        </div>
      </form>
      <p>
        Resultado: {{ estado.resultado }}
      </p> 
    </div>
</template>

<style scoped>
  .container{
    max-width: 500px;
    background-color: rgb(247, 235, 221);
    padding: 50px;
    margin-top: 80px;
  }
</style>