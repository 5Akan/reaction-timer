<template>
  <div class="block" v-if = "showLock">
      Click Me 
  </div>
</template>

<script>
export default {
    data(){
        return {
            showLock:false
        }
    },
    methods:{},
props:['delay'],
// LifeCycle Hook
mounted(){//Works when the items in template are mountes
    console.log('Components Mounted');
    setTimeout(()=>{});
},
updated(){

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