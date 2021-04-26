<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{text}}</h2>
    <div class="text-2xl mt-4 mb-10">
      {{ timestamp }}
    </div>
  </div>
</template>

<script>
  import moment from 'moment';
  import 'moment/locale/pt-br';

  export default {
    name: 'DataTitle',
    props: ['text', 'dataDate'],
    computed: {
      timestamp: function() {
        return moment(this.dataDate).utc().format('D/MM/YYYY, h:mm:ss a', 'pt-br')
      }
    }

  }
</script>
