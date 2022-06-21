
<template>
<div>
    <HeaderTitle v-bind:title='Hello' />
    <SearchPanel />

    <ToDoList :todos='todos' />
    <AddFormsTask />
</div>
</template>

<script>
import HeaderTitle from "./components/HeaderTitle.vue";
import SearchPanel from "./components/SearchPanel.vue";
import ToDoList from "./components/ToDoList.vue";
import AddFormsTask from "./components/AddFormsTask.vue";
export default {
  components: {
    HeaderTitle,
    SearchPanel,
    ToDoList,
    AddFormsTask
  },
  data(){
    return {
      todos: [
        {id: 1, text: 'Learn Vue.js'}, 
        {id: 2, text: "Drink Coffee"}
      ],
    }
  }
}
</script>
