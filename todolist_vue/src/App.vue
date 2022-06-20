
<template>
<div>
    <HTittle />


    <p v-if="isLogin === true">Welcome back!</p>
    <p v-else>Please, authorize!</p>
    
    <p v-show="isLogin">Show example</p>

    <ul>
      <!-- <li v-for="task in todos">Learn VueJS</li> -->
      <li>Drink Coffee</li>
    </ul>
    <div>
      <input v-bind:type="passwordVisible?'text':'password'" name="" id="inp"/>
      <button v-on:click="passwordVisible = !passwordVisible">Button</button>
    </div>
</div>
</template>

<script>
import HeaderTitle from "./components/HeaderTitle.vue";
export default {
  components: {
    HTittle: HeaderTitle
  },
  data(){
    return {
      title: 'Welcome to my ToDoList',
      isLogin: false, 
      todos: ['Learn Vue.js', "Drink Coffee"],
      passwordVisible: false
    }
  }
}
</script>

<style>

</style>