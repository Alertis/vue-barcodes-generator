<template>
    <span v-if="data.length > 0">
        <svg class="barcode" v-for="(b,i) in data" :key="i" v-bind="getProps" :jsbarcode-value="b"></svg>
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
  computed:{
    getProps: function(){
      let props = []
      Object.keys(this.config).map(c => {
        props.push({['jsbarcode-'+c.toLowerCase()]: this.config[c]})
      })
      return props
    }
  },
  props: {
    data: Array,
    config: Object
  },
}
</script>

<style lang="css" scoped>
  @import "../assets/css/style.css";
</style>
