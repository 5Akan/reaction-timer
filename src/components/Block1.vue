<template>
  <div class="block" v-if = "showBlock">
      Click Me 
  </div>
</template>

<script>
export default {
    data(){
        return {
            showBlock:false,
            timer:null,
            reactionTime:0
        }
    },
props:['delay'],
// LifeCycle Hook
mounted(){//Works when the items in template are mounts
    
    setTimeout(()=>{
        this.showBlock = true;
        this.startTimer();
        console.log(this.delay)
    },this.delay);
},
methods:{
        startTimer(){
            this.timer = setInterval(()=>{//the method is set to the timer property so it can be cleared in the stopInterval function
                this.reactionTime +=10;
            },10)
        },
        stopTimer(){
            clearInterval(this.timer);
        }   
         }
}
</script>

<style>
    .block{
        width: 400px;
        border-radius: 20px;
        background: #0faf87;
        color: white;
        text-align: center;
        padding: 100px 0; 
        margin: 40px auto;
    }
</style>