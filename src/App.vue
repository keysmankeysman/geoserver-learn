<template>
  <div id="app">
    <!-- <First></First> -->
    <h2>WFS</h2>
    <WfsFirst></WfsFirst>
    <h2>OWS</h2>
    <OwsFirst></OwsFirst>
    <h2>WMS</h2>
    <WmsFirst></WmsFirst>
  </div>
</template>

<script>
import WfsFirst from './components/wfs/WfsFirst'
import OwsFirst from './components/ows/OwsFirst'
import WmsFirst from './components/wms/WmsFirst'

export default {
  // components: { First, Second },
  components: { WfsFirst, OwsFirst, WmsFirst },
  data() {
    return {

    }
  },
  methods: {
 
  }
}

</script>


<style lang="scss">


</style>
