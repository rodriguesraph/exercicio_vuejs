<script setup>

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
          <select class="form-control">
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
          </select>
        </div>
      </div>
      <div class="row">
        <div class="col-3">
          <form>
            <input type="number" placeholder="Valor 1" class="form-control">
          </form>
        </div>
        <div class="col-1">
          <h2>+</h2>
        </div>
        <div class="col-3">
          <form>
            <input type="number" placeholder="Valor 2" class="form-control">
          </form>
        </div>
        <div class="col-1">
          <h2>=</h2>
        </div>
        <div class="col-3">
          <h2>1000</h2>
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
