<template>
  <div id="app">
    <InputArea v-if="!inputted" @inputted="showResult" />
    <ResultPenname v-if="inputted" :inputData="inputData"/>
  </div>
</template>

<script>
import InputArea from './components/InputArea.vue'
import ResultPenname from './components/ResultPenname.vue'

export default {
  name: 'app',
  data(){
    return {
      inputData: {
        name: '',
        sex: 0,
      },
      inputted: false,
    }
  },
  methods:{
    showResult(selectData){
      this.inputData.name = selectData.name;
      this.inputData.sex = selectData.sex;
      this.inputted=true;
    }
  },
  components: {
    InputArea,
    ResultPenname,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

}
</style>
