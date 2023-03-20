<template>
  <div>
      
      <button @click="sendRequest()">Отправить capabilities запрос</button>  

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
      axios.get('/geoserver/wms?service=wms&request=GetCapabilities')
        .then(res => console.log(res))
    }
  }
}

</script>


<style lang="scss">


</style>
