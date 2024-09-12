<script setup>
import { reactive } from 'vue';

const dados = reactive({
  valor1: 0,
  valor2: 0,
  operacao: 'adicao',
  simbolo: '+',
  resultado: 0,
})

const fazCalculo = () => {
  const { operacao } = dados;

  switch (operacao) {
    case 'subtracao':
      dados.resultado = dados.valor1 - dados.valor2;
      dados.simbolo = '-';
      return dados.resultado;
    case 'multiplicacao':
      dados.resultado = dados.valor1 * dados.valor2;
      dados.simbolo = '*';
      return dados.resultado;
    case 'divisao':
      dados.resultado = dados.valor1 / dados.valor2;
      dados.simbolo = '/';
      return dados.resultado;
    default:
      dados.resultado = parseFloat(dados.valor1) + parseFloat(dados.valor2);
      dados.simbolo = '+';
      return dados.resultado;
  }
}

</script>

<template>
  <div class="container">
    <div class="block">
      <div class="row">
        <div class="col title">
          <h1><i class="bi bi-calculator-fill"></i>Calculadora Simples</h1>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <select @change="evento => dados.operacao = evento.target.value" class="form-control">
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
          </select>
        </div>
      </div>
      <div class="row">
        <div class="col-3">
          <form @keyup="fazCalculo">
            <input :value="dados.valor1" @keyup="evento => dados.valor1 = evento.target.value" type="number"
              placeholder="Valor 1" class="form-control">
          </form>
        </div>
        <div class="col-1">
          <h2>{{ dados.simbolo }}</h2>
        </div>
        <div class="col-3">
          <form @keyup="fazCalculo">
            <input :value="dados.valor2" @keyup="evento => dados.valor2 = evento.target.value" type="number"
              placeholder="Valor 2" class="form-control">
          </form>
        </div>
        <div class="col-1">
          <h2>=</h2>
        </div>
        <div class="col-3">
          <h2>{{ dados.resultado }}</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.block {
  background-color: rgb(219, 248, 243);
  padding: 16px;
  border-radius: 16px;
}

.title {
  align-items: center;
  text-align: center;
  margin-bottom: 8px;
}

.title h1 {
  background: -webkit-linear-gradient(45deg, #09009f, #00ff95 80%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: bold;
}

.title i {
  margin-right: 8px;
}

h2 {
  align-items: center;
  text-align: center;
}

select {
  margin-bottom: 16px;
}

form input {
  width: 100%;
}
</style>
