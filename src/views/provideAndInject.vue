<template>
 <div>
   <h1>{{themeColor}}</h1>
 </div>
</template>

<script>
import { inject } from '@vue/composition-api'
 export default {
  data () {
    return {

    }
  },
  components: {

  },
  setup () {
    const themeColor = inject("globalColor");
    return {
      themeColor
    }
  }
 }
</script>

<style>

 
</style>
