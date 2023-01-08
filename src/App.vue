<template>
  <div id="app">
    <BarcodeGenerator  :inputs="inputs"/>
  </div>
</template>

<script>
import BarcodeGenerator from './components/App.vue'

export default {
  name: 'App',
  data: function(){
    return {
      inputs: [
        {name: 'year', title:'Yıl', val: ''},
        {name: 'month', title:'Ay', val: ''},
        {name: 'code', title:'Ürün Kodu', val: ''}
      ]
    }
  },  
  components: {
    BarcodeGenerator
  }
}
</script>
x
