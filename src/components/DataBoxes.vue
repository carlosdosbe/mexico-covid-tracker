<template>
  <div class="grid md:grid-cols-2 gap-4 mb-10">
    
    <div class="shadow-md bg-indigo-100 p-10 text-center rounded">
      <h3 class="text-3xl text-indigo-900 font-bold mb-4"><i class="fas fa-head-side-mask"></i> Casos.</h3>
      
      <div class="text-2xl mb-4">
        <span class="font-bold">Nuevos:</span>
        {{ numberWithCommas(stats2.NewConfirmed) }}
      </div>
      
      
      <div class="text-2xl mb-4">
        <span class="font-bold">Activos:</span>
        {{numberWithCommas(stats.Active)}}
      </div>

      <div class="text-2xl mb-4">
        <span class="font-bold">Confirmados:</span>
        {{numberWithCommas(stats.Confirmed)}}
      </div>
    </div>

    <div class="shadow-md bg-indigo-300 p-10 text-center rounded">
      <h3 class="text-3xl text-white-900 font-bold mb-4"><i class="fas fa-skull-crossbones"></i> Muertes.</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">Nuevas:</span>
        {{ numberWithCommas(stats2.NewDeaths) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Totales:</span>
        {{ numberWithCommas(stats2.TotalDeaths) }}
      </div>
    </div>

    <div class="shadow-md bg-indigo-300 p-10 text-center rounded">
      <h4 class="text-xl text-white-900 font-bold mb-4">Últimos datos ingresados.</h4>
      <h3 class="text-3xl text-white-900 font-bold mb-4"><i class="fas fa-skull-crossbones"></i> {{stats3.Province}} .</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">Confirmados:</span>
        {{ numberWithCommas(stats3.Confirmed) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Muertes:</span>
        {{ numberWithCommas(stats3.Deaths) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Recuperados:</span>
        {{ numberWithCommas(stats3.Recovered) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Avtivos:</span>
        {{ numberWithCommas(stats3.Active) }}
      </div>
    </div>
    
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
    name: 'DataBoxes',
    props: ['stats', 'stats2', 'stats3'],
    methods: {
      numberWithCommas(x) {
        return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')
      },
    },
  }
</script>
