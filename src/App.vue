<script setup>
import { reactive, computed } from 'vue';

const estado = reactive({
  numero1: 0,  
  numero2: 0,  
  operacao: '+' 
});

const resultado = computed(() => {
  switch (estado.operacao) {
    case '+':
      return estado.numero1 + estado.numero2;
    case '-':
      return estado.numero1 - estado.numero2;
    case '*':
      return estado.numero1 * estado.numero2;
    case '/':
      return estado.numero1 / estado.numero2;
  }
});
</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 text-primary-emphasis bg-primary-subtle border border-primary-subtle rounded-3 text-center">
      <h1>Calculadora Aritmética</h1>
      <p>
        Exercício de VueJS do Curso Full Stack Designer - EBAC
      </p>
    </header>
  </div>
  <div class="container mt-5">
    <div class="row justify-content-center">

      <div class="form-group col-md-3">
        <label for="numero1">Digite o primeiro número</label>
        <input id="numero1" type="number" v-model.number="estado.numero1" class="form-control">
      </div>

      <div class="form-group col-md-3">
        <label for="operacao">Escolha a operação</label>
        <select id="operacao" v-model="estado.operacao" class="form-control">
          <option value="+">Adição</option>
          <option value="-">Subtração</option>
          <option value="*">Multiplicação</option>
          <option value="/">Divisão</option>
        </select>
      </div>

      <div class="form-group col-md-3">
        <label for="numero2">Digite o segundo número</label>
        <input id="numero2" type="number" v-model.number="estado.numero2" class="form-control">
      </div>

      <div class=" mt-5 text-primary-emphasis text-center">
        <h4>O resultado desta operação é:</h4> <br /><h2>{{ resultado }}</h2>
      </div>

    </div>
  </div>

</template>


<style scoped>
</style>
