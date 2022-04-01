<template>
    <div class="progress">
      <div class="progress-bar bg-info" role="progressbar" :style="{width:progressPercentValue + '%'}" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">
        {{this.currentItemCount}}/10
      </div>
    </div>
</template>

<script>
  import {eventBus} from '../main.js'
  export default{
    data:function(){
      return{
        currentItemCount:0,
        progressPercentValue:0
      }
    },
    created(){
      eventBus.$on('progressBarUpdatedValue',(lenproductlist)=>{
        this.currentItemCount = lenproductlist
        this.progressPercentValue = lenproductlist * 10
      })
    }
  }
</script>

<style scoped>

</style>
