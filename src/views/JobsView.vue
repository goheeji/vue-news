<template>
  <div>
    <div v-for="(job, index) in jobs" :key="index">
      {{job.title}}
    </div>
  </div>
</template>

<script>
import { fetchJobsList } from '../api/index';
export default {
  data(){
    return{
      jobs:[]
    }
  },
  created(){
    fetchJobsList()
      .then(response => this.jobs=response.data)
      .catch(function(error){
        console.log(error);
      })
  }


}
</script>

<style>

</style>