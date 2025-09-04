<script setup>
import Formulario from './components/Formulario.vue';
</script>

<template>
  <div id="app" class="container mt-5">
    <header class="text-center mb-4">
      <h1 class="text-primary">Mi Aplicación con Formularios</h1>
      <p class="lead">Componente de formulario interactivo</p>
    </header>
    
    <Formulario />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
