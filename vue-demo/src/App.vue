<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
//import HelloWorld from './components/HelloWorld.vue'

export default{
  data(){
    return{
      num: 2,
      name: "zhangsan",
      html_info: '<h2>title</h2>'
    }
  },
  // 方法
  methods:{
    increase(){
      this.num = 14
    }
  },
  // 计算属性,依赖值不变，不会重复调用（有缓存）
  computed:{
    //1. 方式一：当作方法
    // reverseMsg: function(){
    //   return this.name.split('').reverse().join('');
    // }
    //2. 方式二：当作计算属性，有getter 和 setter， 一般没有set方法，意思是属性是只读属性
    reverseMsg:{
      // 当调用reverseMsg属性时候，自动执行get方法，相当于方式一
      get: function(){
        return this.name.split('').reverse().join('');
      },
      // set 在更改or设置属性时候调用
      set:function(newvalue){

      }

    }
  },
  // watch: 监听 数据的变化
  watch:{
    // 监听num是否发生变化
    num:function(newvalue,oldValue){
      console.log(newvalue)
      console.log(oldValue)
      // 执行异步操作，或者复杂的逻辑代码


    }
  }
}
</script>

<template>
<p>{{name}}</p>
<p>{{num}}</p>
<p>{{html_info}}</p>
<p v-html="html_info"></p>
<button @click="increase">Change num to 14</button>
<!-- 方法在这边直接调用 -->
<p>{{reverseMsg}}</p>




</template>