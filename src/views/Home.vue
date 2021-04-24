<template>
  <main v-if="!loading">
    <DataTitle :text="title" :dataDate="dataDate" />
    <DataBoxes :stats="stats" :stats2="stats2" :stats3="stats3"/>
  </main>
  <main class="flex flex-col aling-center justify-center text-center" v-else>
    <div class="text-gray-500 text-3xl mt-10 mb-6">
      Fetching data
    </div>
    <img :src="loadingImage" class="w-24 m-auto" alt="">
  </main>
</template>

<script>

import DataTitle from '@/components/DataTitle'
import DataBoxes from '@/components/DataBoxes'
import Info from '@/components/Info'

export default {
  name: 'Home',
  components: {
    DataTitle,
    DataBoxes,
    Info,
  },
  data(){
    return {
      loading: true,
      title: 'México',
      dataDate: '',
      status: {},
      countries: [],
      loadingImage: require('../assets/loading.gif'),
    }
  },
  methods: {
    async fetchCovidData(){
      const res = await fetch('https://api.covid19api.com/total/country/mexico')
      const data = await res.json()
      return data
    },
    async fetchCovidDataGlobal(){
      const res = await fetch('https://api.covid19api.com/summary')
      const data = await res.json()
      return data
    },
    async fetchCovidDataLive(){
      const res = await fetch('https://api.covid19api.com/live/country/mexico/status/confirmed')
      const data = await res.json()
      return data
    }
  }, 
  async created(){
    const data = await this.fetchCovidData()
    const data2 = await this.fetchCovidDataGlobal()
    const data3 = await this.fetchCovidDataLive()
    const p = data2.Countries
    var mex;
    for(var i = 0; i < p.length; i++)
    {
      if(p[i].CountryCode == "MX")
      {
        mex = p[i]
      }
    }

    this.dataDate = data.Date
    this.stats = data[data.length-1]
    this.stats2 = mex
    this.stats3 = data3[data3.length-1]
    this.loading = false

    setTimeout(
      function(){
        location.reload();
      }, 60000
    )
  },
}

</script>
