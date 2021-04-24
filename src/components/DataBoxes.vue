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

  </div>
</template>

<script>

  export default {
    name: 'DataBoxes',
    props: ['stats', 'stats2'],
    methods: {
      numberWithCommas(x) {
        return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')
      },
    },
  }
</script>
