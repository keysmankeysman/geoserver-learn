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
      axios.get('http://gisfpd.petrosoft.su/geoserver/wms?service=WMS&version=1.1.1&request=DescribeLayer&layers=fpd:all_boundaries_oktmo&output_format=application/json')
        .then(res => console.log(res))
    }
  }
}

</script>


<style lang="scss">


</style>
