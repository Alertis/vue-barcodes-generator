<template>
    <span v-if="data.length > 0">
        <svg class="barcode" v-for="(b,i) in data" :key="i"
            :jsbarcode-format="config.format ? config.format : 'auto'"
            :jsbarcode-value="b"
            :jsbarcode-fontsize="config.fontSize"
            :jsbarcode-fontoptions="config.fontOption"
            :jsbarcode-width="config.width"
            :jsbarcode-height="config.height"
            :jsbarcode-displayvalue="config.displayValue"
            :jsbarcode-text="config.text"
            :jsbarcode-font="config.font"
            :jsbarcode-textalign="config.textAlign"
            :jsbarcode-textposition="config.textPosition"
            :jsbarcode-textmargin="config.textMargin"
            :jsbarcode-background="config.background"
            :jsbarcode-linecolor="config.lineColor"
            :jsbarcode-margin="config.margin"
            :jsbarcode-margintop="config.marginTop"
            :jsbarcode-marginleft="config.marginLeft"
            :jsbarcode-marginbottom="config.marginBottom"
            :jsbarcode-marginright="config.marginRight" ></svg>
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
    data: Array,
    config: Object
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
