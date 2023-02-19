<template>
  <div id="app">
    <BarcodeGenerator  
      :inputs="inputs"
      :buttonText="'Oluştur'"
      :buttonClass="'button'"
      :barcodeConfig="barcodeConfig"
    />
  </div>
</template>

<script>
import BarcodeGenerator from './components/App.vue'

export default {
  name: 'App',
  data: function(){
    return {
      inputs: [],
      barcodeConfig: {
        format: 'auto',
        fontSize: 10,
        fontOption: 'italic',
        width: 1,
        displayValue: false,
        textAlign: 'center',
        textPosition: 'bottom',
        textMargin: 10,
        height: 10
      }
    }
  },  
  components: {
    BarcodeGenerator
  }
}
</script>
<style lang="css" scoped>
  @import "./assets/css/style.css";
</style>