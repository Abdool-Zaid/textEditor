<script setup>
import { onMounted } from "vue";
document.designMode='on'
let text=localStorage.text?localStorage.text:''
onMounted(() => {
  mainDIV.innerHTML=text
  window.addEventListener('keypress',(event)=>{
    console.log(mainDIV.innerHTML)
  })
  let listeners= ()=>{
    if (mainDIV.innerHTML!=undefined){
      localStorage.setItem('text',mainDIV.innerHTML) 
    }
setTimeout(()=>{
  listeners()
},750)   
  }
  listeners()
});
</script>

<template>
<div id="mainDIV"></div>
</template>

<style scoped>
#mainDIV{
width: 100vw;
height: 100vh;
  overflow-wrap: break-word;
}
</style>
