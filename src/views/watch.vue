<template>
 <div>
   <h1>Watch</h1>
 </div>
</template>

<script>
import { ref, watch, reactive } from '@vue/composition-api'
 export default {
  data () {
    return {
      outsideCount: ""
    }
  },
  components: {

  },
  setup() {
// 直接打印出 ++++++1
    // const watchCount = ref(0)
    // watch(() => {
    //   console.log("++++++", watchCount.value)
    // })
    // watchCount.value++

// ++++++0
// ++++++1
    // const watchCount = ref(0)
    // watch(() => {
    //   console.log("++++++", watchCount.value)
    // })
    // setTimeout(() =>  {
    //   watchCount.value++
    // })

// 监视reactive里面的值
    // const watchState = reactive({count: 0})
    // watch(
    //   () => watchState.count, //如果没有这个下面直接打印出来就是一串函数
    //   (count, preCount) => {
    //     console.log(".>>>>>>>", count, preCount)
    //   }
    // )
    // setTimeout(watchState.count ++)

//  监视ref里面的值
    // const watchRefCount = ref(0)
    // watch((watchRefCount, (watchRefCount, preWatchRefCount) => {

    // }))

// 我想在data里面玩  所以3.0里面watch是怎么监听data里面的数据的呢
  // watch((outsideCount, (outsideCount, outsideCountPre) => {
  //   console.log(outsideCount)
  // }))

// 监视多个reactive数据源
    // console.log(">>>>>>")
    // const state = reactive({count: 0, name: 'zs'})
    // watch(
    //   [() => state.count, () => state.name],
    //   ([count, name], [preCount, preName]) => {
    //     console.log("count: " + count, "preCount: " + preCount);
    //     console.log("name: " + name, "preCount: " + preName);
    //   },
    //   {
    //     lazy: true // 在 watch 被创建的时候，不执行回调函数中的代码  //如果不这么设置就会报错
    //   }
    // )
    // setTimeout(() => {
    //   state.count++
    //   state.name = 'ls'
    // }, 2000)

    // 监视多个ref
    // const count = ref(0);
    // const name = ref('zs');
    // watch([count, name], ([count, name], [preCount, preName]) => {
    //   console.log("count"+ count, "name"+ name)
    // }, {
    //   lazy: true
    // })
    // setTimeout(() => {
    //   count.value++
    //   name.value = "ls"
    // })

// stop()
    // const count = ref(0);
    // const name = ref('zs');
    // const stop = watch([count, name], ([count, name], [preCount, preName]) => {
    //   console.log("count"+ count, "name"+ name)
    // }, {
    //   lazy: true
    // })
    // setInterval(() => {
    //   count.value++
    //   name.value = "ls"
    // }, 500)
    // setTimeout(() => {
    //   stop()
    // }, 2000)

// 清除无效的异步操作，但是timeout要是一个请求呢，应该怎么清除
    // 定义响应式数据 keywords
    // const keywords = ref('')

    // // 异步任务：打印用户输入的关键词
    // const asyncPrint = val => {
    //   // 延时 1 秒后打印
    //   return setTimeout(() => {
    //     console.log(val)
    //   }, 1000)
    // }

    // // 定义 watch 监听
    // watch(
    //   keywords,
    //   (keywords, prevKeywords, onCleanup) => {
    //     // 执行异步任务，并得到关闭异步任务的 timerId
    //     const timerId = asyncPrint(keywords)

    //     // 如果 watch 监听被重复执行了，则会先清除上次未完成的异步任务
    //     onCleanup(() => clearTimeout(timerId))
    //   },
    //   // watch 刚被创建的时候不执行
    //   { lazy: true }
    // )

    // // 把 template 中需要的数据 return 出去
    // return {
    //   keywords
    // }


  }
 }
</script>

<style>

 
</style>
