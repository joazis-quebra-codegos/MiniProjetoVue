<script setup lang="ts"></script>

<template>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">
  <div class="cadastro" style="display: flex; justify-self: center;width:50%; flex-direction: column; margin-top: 20px;">
    <label class="form-label">Nome</label>
 <input class="form-control" type="text" placeholder="Nome" aria-label="Nome">
  <label class="form-label">Email</label>
 <input class="form-control" type="email" placeholder="Email" aria-label="Email">
  <label  class="form-label">Salario</label>
 <input class="form-control" type="email" placeholder="Salário" aria-label="salario">
  </div>


  

  <table>
    <thead>
      <tr>
        <th>Nome</th>
        <th>Email</th>
        <th>Cargo</th>
        <th>Salario</th>
        <th>Ações</th>
      </tr>
      <tbody>
        <tr></tr>
      </tbody>

    </thead>
  </table>
</template>

<style scoped>
  body{
    display: flex;
    justify-content: center;
  }
  .cadastro{
    width: 50%;
  }
</style>
