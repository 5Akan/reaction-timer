<template>
  <p class="rank">The result is {{ score }} ms </p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
   props: ['score'],
   data(){
       return{
           rank:null
       }
   },
   mounted(){
       if(this.score < 250){
           this.rank = "Lightening Fingers";
       }else if(this.score > 250  & this.score < 350 ){
           this.rank = "Speedstar";
       }else if(this.score > 350 & this.score < 400 ){
           this.rank = "Fast";
       }else{
           this.rank = "Slow";
       }
   }
    
}
</script>

<style>
    .rank{
        font-size: 1.5em;
        color: #0faf87;
        font-weight: bold;
    }
</style>