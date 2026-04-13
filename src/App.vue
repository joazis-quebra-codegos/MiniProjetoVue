<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { computed, ref, VueElement } from 'vue'
import type Funcionario from './model/Funcionario';
const cargo = ref('')
const erro = ('')

function validar(){
  const erros: string[] = []

  if (!funcionario.value.nome){
    erros.push("Nome é obrigatório")
  }

  if (!funcionario.value.email){
    erros.push("Email é obrigatório")
  }

  if (!funcionario.value.cargo){
    erros.push("Cargo é obrigatória")
  }

  if (!funcionario.value.salario){
    erros.push("Salario é obrigatório")
  }

  return erros
}

function enviar(){
  const erros = validar()

  if (erros.length > 0){
    alert(erros.join('\n')) // quebra de linha
  } else {
    alert("Funcionário válido ✅")
  }
}

const funcionario = ref({} as Funcionario)
const funcionarios = ref([
  {
    id: 1,
    nome: "João",
    email: "joao@email",
    cargo: "estudante",
    salario: 0
  }
]as Funcionario[])

</script>

<template>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">


  <div class="cadastro" style="display: flex; justify-self: center;width:50%; flex-direction: column; margin-top: 20px;">
  <label class="form-label">Nome</label>
  <input class="form-control" type="text" placeholder="Nome" aria-label="Nome">
  <label class="form-label">Email</label>
  <input class="form-control" type="email" placeholder="Email" aria-label="Email">
  <label for="form-label">Cargo</label>
  <input class="form-control" type="text" placeholder="Insira o cargo aqui" v-model="cargo">
  <label  class="form-label">Salario</label>
  <input class="form-control" type="email" placeholder="Salário" aria-label="salario">
  </div>


  <table class="table" style="width: 50%;">
    <thead>
      <tr>
        <th scope="col">Nome</th>
        <th scope="col">Email</th>
        <th scope="col">Cargo</th>
        <th scope="col">Salario</th>
        <th scope="col">Ações</th>
      </tr>
      <tbody>
        <tr v-for="funcionario in funcionarios" :key="funcionario.id"></tr>
      </tbody>
    </thead>
  </table>

  <h1>{{  }}</h1>
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
