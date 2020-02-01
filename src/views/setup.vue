<template>
 <div>
   <p>count: {{count}}</p>
   <p>object.foo: {{object.foo}}</p>
   <p>object.count: {{object.count}}</p>
  <button @click="handleCount">changeCount</button>
  <button @click="handleFoo">changeFoo</button>

  <p>ToRefs: {{date}} ------ {{eat}}</p>
  <button @click="handlehangeRefs">changeToRefs</button>
 </div>
</template>

<script>
import { ref, reactive, toRefs } from '@vue/composition-api'
 export default {
  data() {
    return {
      name: "qsj"
    }
  },
  props: {
    setupData: {
      default: null,
      type: Object
    }
  },
  computed: {
    doubleName() {
      return name.repeat(2)
    }
  },
  components: {

  },
  setup(props, context) {
    console.log("context is", context)
    console.log("this is this", this)
    console.log(props.setupData)
    const count = ref(0)
    // 注意这类count有.value的问题
    const object = reactive({ 
      foo: 'bar',
      count: count.value
    })
    const ToRefs = reactive({
      date: "2019-01-24",
      eat: "rice"
    })
    console.log("toRefs", toRefs(object))
    return {
      count,
      object,
      ...ToRefs
    }
  },
  mounted() {
  },
  methods: {
    handleCount() {
      this.count ++
      console.log("count", this.count)
    },
    handleFoo() {
      this.object.foo = this.object.foo + "changeFoo"
      console.log("foo", this.object.foo)
    },
    handlehangeRefs() {
      this.date =  this.date + "yestoday"
      this.eat += "like"
      console.log("ToRefs", this.date, this.eat)
      //  用了toRef以后就不会改变原来的object
      console.log("object=>", this.object)
    }
  }
 }
</script>

<style>

 
</style>
