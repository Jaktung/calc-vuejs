<script setup>

</script>

<template>
    <div class="container rounded">
      <h1>Calculadora</h1>
      <form>
        <div class="row mb-3">
          <input type="number" required class="form-control mb-3">
          <input type="number" required class="form-control mb-3">
          <select class="form-control mb-4">
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
          </select>
          <button type="submit" class="btn btn-primary">Calcular</button>
        </div>
      </form>
      <h3 class="form-control mt-4">
        2
      </h3>   
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
