<template>
    <div>
        <Form :inputs="inputs" :barcodes="barcodes" /> 
        <BarcodeList :data="barcodes"/>
    </div>
    
  </template>
  
  <script>
  import Form from './Form.vue'
  import BarcodeList from './BarcodeList.vue'

  export default {
    name: 'BarcodeForm',
    data: function(){
      return{
        barcodes: []
      }
    },
    components:{
        Form, BarcodeList
    },
    props: {
      inputs: Array
    },
  }
  </script>
  