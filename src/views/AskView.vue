<template>
  <div>
    <div v-for="( ask, index ) in asks" :key="index">
      {{ask.title}}
    </div>
  </div>
</template>

<script>
import { fetchAskList } from '../api/index.js'

export default {
  data(){
    return{
      asks:[]
    }
  },
  created() {
    fetchAskList()
      .then(response => this.asks = response.data)
      .catch(function(error){
        console.log(error);
      })
  }

}
</script>

<style>

</style>