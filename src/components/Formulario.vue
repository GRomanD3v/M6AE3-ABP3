<script setup>
import { ref } from 'vue';

const estudios = ref('educacion_universitaria');
const opcionesEstudios = [
  { id: 'basica', label: 'Educación Básica', value: 'educacion_basica' },
  { id: 'media', label: 'Educación Media', value: 'educacion_media' },
  { id: 'tecnica', label: 'Educación Técnica', value: 'educacion_tecnica' },
  { id: 'universitaria', label: 'Educación Universitaria', value: 'educacion_universitaria' }
];

const diaSeleccionado = ref('');
const diasDeLaSemana = [
  'Lunes',
  'Martes',
  'Miércoles',
  'Jueves',
  'Viernes',
  'Sábado',
  'Domingo'
];
</script>

<template>
  <div class="container my-5">
    
    <div class="card p-4 shadow-sm">
      <h4 class="mb-3">Selecciona tu nivel de estudios:</h4>
      
      <div v-for="opcion in opcionesEstudios" :key="opcion.id" class="form-check">
        <input class="form-check-input" type="radio" name="tipo_estudios" :id="opcion.id" :value="opcion.value" v-model="estudios">
        <label class="form-check-label" :for="opcion.id">
          {{ opcion.label }}
        </label>
      </div>
      
      <div class="alert alert-info mt-3" v-if="estudios">
        Nivel seleccionado: <strong>{{ estudios }}</strong>
      </div>
    </div>
    
    <div class="card p-4 shadow-sm mt-4">
      <h4 class="mb-3">Selecciona un día de la semana:</h4>
      
      <select class="form-control" v-model="diaSeleccionado">
        <option disabled value="">Por favor, selecciona un día</option>
        <option v-for="dia in diasDeLaSemana" :key="dia" :value="dia">
          {{ dia }}
        </option>
      </select>
      
      <div class="alert alert-success mt-3" v-if="diaSeleccionado">
        Día seleccionado: <strong>{{ diaSeleccionado }}</strong>
      </div>
    </div>
    
  </div>
</template>

<style>
</style>