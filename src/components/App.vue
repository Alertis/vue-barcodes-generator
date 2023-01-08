<template>
    <div>
        <Form 
            :inputs="inputs"
            :barcodes="barcodes"
            :buttonText="buttonText" 
            :buttonClass="buttonClass"
        /> 
        <BarcodeList 
            :data="barcodes"
            :config="barcodeConfig"
        />
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
      inputs: Array,
      buttonText: String,
      buttonClass: String,
      barcodeConfig: Object
    },
  }
  </script>
  