<template>
    <h6>Filtros</h6>
    <div class="filtro-paises">
      <label>Paises:</label>
      <q-select filled v-model="model" :option="origin_country" />
    </div>
  </template>
  
  <style>
  .precios {
    max-width: 200px;
  }
  </style>
  <script>
  
  export default {
    name: "ProgramasFilter",
    data() {
      return {
        model: null,
        origin_country: ["US", "BR", "ZA", "CA","AU","DE"]
      }
    }
  }
  </script>