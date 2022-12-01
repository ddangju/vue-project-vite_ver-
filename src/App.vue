<template>
  

  <!-- 리스트의 경우 -->
  <!-- <div v-for="item in items">
  hi  {{item}}
  </div> -->

  <!-- object의 경우 -->
  <div v-for="(value, key) in items">
    {{ value }}
    {{ key }}
  </div>
  <div v-for="item in items" :key="item.id">
    {{ item }}
  
  </div>
</template>

<script>
// import {reactive} from 'vue';
import { reactive } from 'vue';

  export default {
    setup(){

      // list의 경우
      // const items = reactive([1,2,3,4,5,6])

      // object의 경우
      const items = reactive({ id:1,a:"1" },{ id:2, b:"2" },{ id:3, c:"3"})
      return { items }
    }
 
  }
</script>

<style lang="scss" scoped>

</style>