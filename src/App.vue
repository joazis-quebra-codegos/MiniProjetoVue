<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { computed, ref, VueElement } from 'vue'
const cargo = ref('')

</script>

<template>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">
  <h1>You did it!</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>

  <input class="form-control" type="text" placeholder="Insira o cargo aqui" v-model="cargo">


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

  <h1>{{  }}</h1>
</template>

<style scoped></style>
