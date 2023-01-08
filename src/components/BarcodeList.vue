<template>
    <span v-if="data.length > 0">
        <svg class="barcode" v-for="(b,i) in data" :key="i"
            jsbarcode-format="auto"
            :jsbarcode-value="b"
            :jsbarcode-fontsize="15"
            jsbarcode-fontoptions="bold"></svg>
    </span>
</template>

<script>
import JsBarcode from 'jsbarcode'

export default {
  name: 'Form',
  watch:{
    data: function(){
      setTimeout(() => {
        JsBarcode('.barcode').init()
      }, 1000)

    }
  },
  props: {
    data: Array
  },
}
</script>

<style scoped>
.input{
  margin: .5rem;
  max-width: 200px;
}
.forms{
  display: flex;
  flex-wrap: wrap;
  align-items: center;
}

input{
  width: 50px
}

label{
  font-weight: bold;
  margin: .5rem;
}

button{
  padding: .5rem;
  background-color: green;
  color: white;
  border-radius: 5px;
}
</style>
