<template>
  <div id="translateOutput">
    <h2>{{translatedText}}</h2>
  </div>
</template>

<script>


export default {
  name: 'translateOutput',
  props:[
    "translatedText"	//接受父组件传值
  ]
  
}
</script>

<style>

</style>
