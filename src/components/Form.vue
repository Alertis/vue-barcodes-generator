<template>
    <div class="forms">
      <div class="input" v-for=" i in inputs" :key="i.name" > 
        <label> {{ i.title }}</label>
        <input v-model="i.val" />
      </div>

      <div class="input" > 
        <label> Start Number </label>
        <input v-model="start" />
      </div>

      <div class="input" > 
        <label> Count </label>
        <input v-model="count" />
      </div>

      <div class="input" > 
        <label> Length </label>
        <input v-model="length" />
      </div>

      <button @click="generate"> Generate </button>
    </div>
</template>

<script>

export default {
  name: 'Form',
  data: function(){
    return{
      count: 0,
      length: 0,
      start: 0
    }
  },
  props: {
    inputs: Array,
    barcodes: Array
  },
  methods:{
    generate: function(){
      let bc = ''

      this.inputs.map(i => {
        bc = bc + i.val
      })

      for(let i=parseInt(this.start); i<(parseInt(this.start) + parseInt(this.count)); i++){
        this.barcodes.push(bc + Array(parseInt(this.length)+1-i.toString().length).join('0')+i.toString())
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

button{
  padding: .5rem;
  background-color: green;
  color: white;
  border-radius: 5px;
}
</style>
