<template>
  <div>

      <button @click="sendRequest()">Отправить запрос</button>  

  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      xmlFilter: `
      <?xml version="2.0.0"?>
      <GetFeature
        xmlns:gml="http://www.opengis.net/gml/3.2"
        xmlns="http://www.opengis.net/wfs/2.0"
        xmlns:fes="http://www.opengis.net/fes/2.0"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.opengis.net/wfs/2.0 http://schemas.opengis.net/wfs/2.0.0/wfs.xsd http://www.opengis.net/gml/3.2 http://schemas.opengis.net/gml/3.2.1/gml.xsd" service="WFS" handle="Query01" count="30000" startIndex="0" outputFormat="application/json" version="2.0.0">
        
      <Query
        typeNames="fpd:all_boundaries_oktmo"
        srsName="EPSG:3857"
      >
        
      </Query>
      </GetFeature>
      `
    }
  },
  methods: {
    async sendRequest() {
      console.log('отправить запрос')
      const config = {
        headers: { 'Content-Type': 'text/xml' }
      }
      const { data: features } = await axios.post('/geoserver/wfs?', this.xmlFilter, config)
      // const { data: features } = await axios.post('geoserver/wfs?service=WFS&version=1.0&request=GetFeature&typenames=fpd:all_boundaries_oktmo')
      console.log(features)
    }
  }
}

</script>


<style lang="scss">


</style>
