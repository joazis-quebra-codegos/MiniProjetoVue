<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { computed, ref, VueElement } from 'vue'
const cargo = ref('')

</script>

<template>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">

  <input class="form-control" type="text" placeholder="Insira o cargo aqui" v-model="cargo">

  <div class="cadastro" style="display: flex; justify-self: center;width:50%; flex-direction: column; margin-top: 20px;">
    <label class="form-label">Nome</label>
 <input class="form-control" type="text" placeholder="Nome" aria-label="Nome">
  <label class="form-label">Email</label>
 <input class="form-control" type="email" placeholder="Email" aria-label="Email">
  <input class="form-control" type="text" placeholder="Insira o cargo aqui" v-model="cargo">
  <label for="form-label">Cargo</label>
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
        <tr> </tr>
      </tbody>

    </thead>
  </table>
<<<<<<< HEAD

  <h1>{{  }}</h1>
=======
>>>>>>> 7bf2c6e7c41a2fe3660c83876dff5cfc9db24543
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
