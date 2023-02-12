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
        {name: 'length', title: 'Barcode No Length', val: 2},
      ],
      buttonText: 'String',
      buttonClass: String,
      barcodeConfig: Object,

    }
  }
}
</script>
