<template>
  <div class="grid md:grid-cols-2 gap-4 mb-10">
    <div class="shadow-md bg-gray-100 p-10 text-center rounded">
      <p class="mb-5">
        Este portal se actualiza cada minuto automáticamente, sin embargo la base de datos se actualiza esporádicamente a lo largo del día.
        <br><br>
        Los datos fueron tomados de la API de covid19api.com, que reune los datos del Centro de Ciencia e Ingeniería de Sistemas (CSSE) de la Universidad Johns Hopkins. Mismos datos que son usados en la mayoría de búsquedas en Google sobre casos de covid.
      </p>
      <h3 class="font-bold">Más información en</h3> 
      <a href="https://covid19.ciga.unam.mx/" target="_blank"><i class="fas fa-link"></i> CIGA UNAM</a>
      <br>
      <a href="https://covid19api.com/" target="_blank"><i class="fas fa-link"></i> API</a>
      <br>
      <a href="https://systems.jhu.edu/research/public-health/ncov/" target="_blank"><i class="fas fa-link"></i> Portal coivd de Johns Hopkins CSSE</a>
    </div>
  </div>
</template>

<script>

  export default {
    name: 'Info',
  }
</script>