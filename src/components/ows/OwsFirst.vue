<template>
  <div>
      
      <button @click="sendRequest()">Отправить get запрос</button>  

  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {

    }
  },
  methods: {
    async sendRequest() {
      axios.get('/geoserver/ows?service=WMS&request=GetLegendGraphic&format=image%2Fpng&width=20&height=20&layer=fpd%3Arosreestr_realty')
        .then(res => console.log(res))
    }
  }
}

</script>


<style lang="scss">


</style>
