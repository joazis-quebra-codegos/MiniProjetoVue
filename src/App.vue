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

  
  <div class="cadastro" style="display: flex; justify-self: center;width:70%; flex-direction: column; margin-top: 20px;">
    <label class="form-label">Nome</label>
    <input class="form-control" type="text" placeholder="Nome" aria-label="Nome" v-model="funcionario.nome">
    <label class="form-label">Email</label>
    <input class="form-control" type="email" placeholder="Email" aria-label="Email" v-model="funcionario.email">
    <label for="form-label">Cargo</label>
    <input class="form-control" type="text" placeholder="Insira o cargo aqui" v-model="funcionario.cargo">
    <label  class="form-label">Salario</label>
    <input class="form-control" type="number" placeholder="Salário" aria-label="salario" v-model="funcionario.salario">
  </div>

  <button @click="enviar" type="submit">Enviar </button>


  <table class="table">
    <thead>
      <tr>
        <th scope="col">Nome</th>
        <th scope="col">Email</th>
        <th scope="col">Cargo</th>
        <th scope="col">Salario</th>
        <th scope="col">Ações</th>
      </tr>
    </thead>
      <tbody>
        <tr v-for="funcionario in funcionarios" :key="funcionario.id">
          <td>{{ funcionario.nome }}</td>
          <td>{{ funcionario.email }}</td>
          <td>{{ funcionario.cargo }}</td>
          <td>{{ funcionario.salario }}</td>
          <td><button class="btn btn-danger" @click="removerUsuario(id)"></button><button class="btn btn-warning"></button></td>
        </tr>
      </tbody>
    
  </table>
</template>

<style scoped>

</style>
