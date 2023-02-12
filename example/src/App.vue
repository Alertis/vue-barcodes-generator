<template>
  <div id="app">
      <VueBarcodes 
        :inputs="inputs"
        :buttonText="buttonText"
        :buttonClass="buttonClass"
        :barcodeConfig="barcodeConfig"
      />
  </div>
</template>

<script>
import VueBarcodes from 'vue-barcodes-generator'

export default {
  name: 'App',
  components:{
    VueBarcodes
  },
  data: function(){
    return{
      inputs: [
        {name: 'start', title: 'First Barcode No', val: 1},
        {name: 'count', title: 'Barcode Count', val: 10},
        {name: 'length', title: 'Number Length', val: 2},
      ],
      buttonText: 'Create',
      buttonClass: 'button',
      barcodeConfig: Object,
    }
  }
}
</script>
<style scoped>
  .button{
    background-color: red
  }
</style>