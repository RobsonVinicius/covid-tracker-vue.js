<template>
  <div class="grid md:grid-cols-2 gap-4">
    <!-- Box 1 --> 
    <div class="shadow-md bg-yellow-200 p-10 text-center rounded">
      <h3 class="text-3xl text-yellow-600 font-bold mb-4">Casos</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">Novos:</span>
        {{ numberWithCommas(stats.NewConfirmed) }}        
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalConfirmed) }}
      </div>
    </div>
    <!-- Box 2 --> 
    <div class="shadow-md bg-red-400 p-10 text-center rounded">
      <h3 class="text-3xl text-red-800 font-bold mb-4">Mortes</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">Novas:</span>
        {{ numberWithCommas(stats.NewDeaths) }}        
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalDeaths) }}
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'DataBoxes',
    props: ['stats'],
    methods: {
      numberWithCommas(x) {
        return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, '.')
      }
    }
  }
</script>
