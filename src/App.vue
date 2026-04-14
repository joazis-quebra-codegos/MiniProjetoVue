<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { computed, ref, VueElement } from 'vue'
import type Funcionario from './model/Funcionario';
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
    erros.push("Cargo é obrigatória")
  }

  return erros
}
function enviar(){
  const erros = validar()

  if (erros.length > 0){
    alert(erros.join('\n'))
  } else {
    alert("Funcionário válido ✅")
    salvarFuncionario()
  }
}

function salvarFuncionario(){
  funcionarios.value.push({
    ...funcionario.value,
    id: Date.now() // gera id simples
  })

  // limpa o formulário
  funcionario.value = {} as Funcionario
}
const funcionario = ref<Funcionario>({
  id: 0,
  nome: '',
  email: '',
  cargo: '',
  salario: 0
})
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
          <td><button class="btn btn-danger"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-backspace-reverse-fill" viewBox="0 0 16 16">
  <path d="M0 3a2 2 0 0 1 2-2h7.08a2 2 0 0 1 1.519.698l4.843 5.651a1 1 0 0 1 0 1.302L10.6 14.3a2 2 0 0 1-1.52.7H2a2 2 0 0 1-2-2zm9.854 2.854a.5.5 0 0 0-.708-.708L7 7.293 4.854 5.146a.5.5 0 1 0-.708.708L6.293 8l-2.147 2.146a.5.5 0 0 0 .708.708L7 8.707l2.146 2.147a.5.5 0 0 0 .708-.708L7.707 8z"/>
</svg></button><button class="btn btn-warning"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-feather" viewBox="0 0 16 16">
  <path d="M15.807.531c-.174-.177-.41-.289-.64-.363a3.8 3.8 0 0 0-.833-.15c-.62-.049-1.394 0-2.252.175C10.365.545 8.264 1.415 6.315 3.1S3.147 6.824 2.557 8.523c-.294.847-.44 1.634-.429 2.268.005.316.05.62.154.88q.025.061.056.122A68 68 0 0 0 .08 15.198a.53.53 0 0 0 .157.72.504.504 0 0 0 .705-.16 68 68 0 0 1 2.158-3.26c.285.141.616.195.958.182.513-.02 1.098-.188 1.723-.49 1.25-.605 2.744-1.787 4.303-3.642l1.518-1.55a.53.53 0 0 0 0-.739l-.729-.744 1.311.209a.5.5 0 0 0 .443-.15l.663-.684c.663-.68 1.292-1.325 1.763-1.892.314-.378.585-.752.754-1.107.163-.345.278-.773.112-1.188a.5.5 0 0 0-.112-.172M3.733 11.62C5.385 9.374 7.24 7.215 9.309 5.394l1.21 1.234-1.171 1.196-.027.03c-1.5 1.789-2.891 2.867-3.977 3.393-.544.263-.99.378-1.324.39a1.3 1.3 0 0 1-.287-.018Zm6.769-7.22c1.31-1.028 2.7-1.914 4.172-2.6a7 7 0 0 1-.4.523c-.442.533-1.028 1.134-1.681 1.804l-.51.524zm3.346-3.357C9.594 3.147 6.045 6.8 3.149 10.678c.007-.464.121-1.086.37-1.806.533-1.535 1.65-3.415 3.455-4.976 1.807-1.561 3.746-2.36 5.31-2.68a8 8 0 0 1 1.564-.173"/>
</svg></button></td>
        </tr>
      </tbody>
    
  </table>
</template>

<style scoped>

</style>
