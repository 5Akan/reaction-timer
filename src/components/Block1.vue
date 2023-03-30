<template>
  <div class="block" v-if = "showBlock">
      Click Me 
  </div>
</template>

<script>
export default {
    data(){
        return {
            showBlock:false
        }
    },
    methods:{},
props:['delay'],
// LifeCycle Hook
mounted(){//Works when the items in template are mountes
    console.log('Components Mounted');
    setTimeout(()=>{
        this.showBlock = true;
        console.log(this.delay)
    },this.delay);
},
updated(){//When mounting occurs. the showBlock is changed to true meaning an update has taken place
    console.log('Component Updated');
},
unmounted(){
    console.log('Component Unmounted');
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