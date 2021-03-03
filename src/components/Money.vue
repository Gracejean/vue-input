<template>

    <div  id="num">
     <input v-model="displayValue" @blur="isInputActive = false" @focus="isInputActive=true"/>
    </div>
</template>

<script>
export default {
    name:'Money',
   props:["value"],
    computed:{
    displayValue:{
      get: function(){
        if(this.isInputActive){
          return this.value.toString()
        }else {
          return this.value.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",")
        }
      },
      set: function(modifiedValue){
        let newValue = parseInt(modifiedValue.replace(/[^\d]/g, ""))
        if(isNaN(newValue)){
          newValue=0
        }
        this.$emit('input', newValue)
      }
    }
  }
}




</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
