<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="hello world"/>
  <h2>hello 欢迎光临</h2>
  <div>请选择菜品</div>
  <div>
    <button 
      @click="selectMenuFun(index)"
      v-for="(item, index) in menu" 
      :key="index">
      {{index}} : {{item}}
    </button>
  </div>
  <div>你选择了{{selectMenu}}</div>
</template>

<script lang="ts">
import {ref} from 'vue'
import HelloWorld from './components/HelloWorld.vue';

// @Options({
//   setup () {
//     const meaus = ref(['花菜','小炒肉'])
//     debugger
//     return {
//       meaus
//     }
//   },
// })
export default {
  name:'app',
  components: {
    HelloWorld
  },
  data () {
    return {
      
    }
  },
  setup () {
    const menu = ref(['小炒肉','花菜']);
    const selectMenu = ref("");
    const selectMenuFun = (index: number) => {
      selectMenu.value = menu.value[index];
    }
    return {
      menu,
      selectMenu,
      selectMenuFun
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
