<script>
export default{
  props:{
    updateTermHandler:{
      type:Function,
      required:true
    }
  },
  data(){
    return{
      term:"",
    }
  },
  methods:{
    changeHandler(e){
      this.term = e.target.value
      this.updateTermHandler(this.term)
    }
  }
}
</script>

<template>
  <input 
    type="text" 
    class="form-control search-input" 
    placeholder="Kinolarni qidirish"
    :value="term"
    @input="changeHandler"
    />
</template>

<style scoped>
.search-input {
  margin-bottom: 1rem;
  padding: 1.5rem;
  background: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0,0.15);
}
</style>
