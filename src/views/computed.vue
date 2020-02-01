<template>
 <div>
   <h1>computed</h1>
   <!-- <div>readOnly: {{plusOne}}</div> -->
 </div>
</template>

<script>
import { ref, reactive, toRefs, computed } from '@vue/composition-api'

 export default {
  data () {
    return {

    }
  },
  components: {

  },
  mounted() {
    // console.log("computedcomponent", ref, reactive, toRefs)
    // 创建一个 ref 响应式数据
    const firstCount = ref(1)
    // 只可以读的计算属性
    const plusOne = computed(() => firstCount.value + 1)
    firstCount.value++ // error
    plusOne.value++ //这样是会报错的，因为他是一个只可以读的计算属性
    console.log("plusOne", plusOne.value) // 输出 2

    // 创建一个可读可写的计算属性
    const secondCount = ref(2)
    const plusTwo = computed({
      get: () => secondCount.value + 1,
      set: val => {
        secondCount.value = 0 - val
      }
    })
    console.log("plusTwo", plusTwo.value)
    plusTwo.value = 9
    console.log("===>plusTwo", plusTwo.value) //先执行set，再执行get

  }
 }
</script>

<style>

 
</style>
