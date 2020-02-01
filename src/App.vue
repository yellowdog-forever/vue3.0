<template>
  <div id="app">
    <!-- <SetUp :setupData="setupData"></SetUp> -->
    <!-- <div>setup：{{count}}, {{ object.foo }}</div> -->
   <!-- 123 {{doubleName}} -->
   <!-- <Computed></Computed> -->
   <!-- <Watch></Watch> -->
<!-- 
   <button @click="changeColor">changeColor</button>
   <ProvideInject></ProvideInject> -->

   <DomRef ref="domRef"></DomRef>
   <button @click="getDomRef">getDomRef</button>
  </div>
</template>

<script>
// import { ref, reactive } from 'vue'
import SetUp from "./views/setup"
import Computed from "./views/computed"
import Watch from "./views/watch"
import ProvideInject from "./views/provideAndInject"
import DomRef from "./views/domRef"
import { provide, ref } from '@vue/composition-api'

export default {
  name: 'app',
  components: {
    // SetUp,
    // Computed,
    // Watch,
    // ProvideInject,
    DomRef
  },
  data() {
    return {
      setupData: {
        name: "setup"
      }
    }
  },
  computed: {
    // html中没有显示
    doubleName() {
      console.log("computed")
      return name.repeat(2)
    },
  },
  setup() {
    // const count = ref(0)
    // const object = reactive({ foo: 'bar' })
    // console.log(count, object)
    // expose to template
    // return {
    //   count,
    //   object
    // }

    // const color = ref("red")
    // provide('globalColor', color) 
    // return {
    //   color
    // }

    // 1. 创建一个组件的 ref 引用
    const domRef = ref(null)

    // 5. 展示子组件中 count 的值
    const showNumber = () => {
      console.log(domRef.value.count)
    }
    return {
      domRef
    }
  },
  beforeCreate() {
    console.log("beforecreate");
  },
  created() {
    console.log("created");
    // console.log("ref", ref);
    // console.log("reactive", reactive);
  },
  beforeMount() {
    console.log("beforeMount")
  },
  mounted() {
    console.log("mounted")
  },
  methods: {
    // changeColor() {
    //   this.color = "blue"
    //   console.log(this.color)
    // }
    
    getDomRef() {
      console.log(this.domRef.value)
    }

  },
  watch: {
    name: {
      immediate: true,
      handler(){
        console.log("watch")
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
