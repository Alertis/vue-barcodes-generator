<template>
    <div class="forms">
      <div class="input" v-for=" i in inputs" :key="i.name" > 
        <label> {{ i.title }}</label>
        <input v-model="i.val" />
      </div>
      <button :class="buttonClass ? buttonClass : 'vbg-button'" @click="generate"> {{buttonText ? buttonText : 'Generate'}} </button>
    </div>
</template>

<script>

export default {
  name: 'Form',
  mounted: function(){
      let start = this.inputs.find( e => e.name == 'start')
      let count = this.inputs.find( e => e.name == 'count')
      let length = this.inputs.find( e => e.name == 'length')

      if(!start)
        this.inputs.push({name: 'start', title: 'Start Number', val: 1})

      if(!count)
        this.inputs.push({name: 'count', title: 'Barcode Count', val: 10})

      if(!length)
        this.inputs.push({name: 'length', title: 'Number Length', val: 4})
  },
  props: {
    inputs: Array,
    barcodes: Array,
    buttonText: String,
    buttonClass: String
  },
  methods:{
    generate: function(){
      let bc = ''
      let start = this.inputs.find( e => e.name == 'start').val
      let count = this.inputs.find( e => e.name == 'count').val
      let length = this.inputs.find( e => e.name == 'length').val

      this.inputs.map(i => {
        if(i.name !== 'start' && i.name !== 'count' && i.name !== 'length')
          bc = bc + i.val
      })

      for(let i=parseInt(start); i<(parseInt(start) + parseInt(count)); i++){
        this.barcodes.push(bc + Array(parseInt(length)+1-i.toString().length).join('0')+i.toString())
      }
    }
  }
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

.vbg-button{
  padding: .5rem;
  background-color: green;
  color: white;
  border-radius: 5px;
}
</style>
