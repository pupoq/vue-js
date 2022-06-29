
<template>
  <div>
      <HeaderTitle />
      <SearchPanel :value="searchPanel" />
      <FilterButtons :value="status" @change="onChangeStatus"/>
      {{status}}
      <ToDoList :todos='todos' :onToggleDone="onDone" :onToggleImportant='onImportant' :id='id' @handleDelete='onDelete'/>
      <AddFormsTask @onAdd='onAdd' @addNewTask="addTask"/>
  </div>
</template>

<script>
      function toggle(array, id) {
            let idx = array.findIndex(item => item.id === id)
            array[idx].done = !array[idx].done
      }
    import HeaderTitle from "./components/HeaderTitle.vue";
    import SearchPanel from "./components/SearchPanel.vue";
    import ToDoList from "./components/ToDoList.vue";
    import AddFormsTask from "./components/AddFormsTask.vue";
    import FilterButtons from "./components/FilterButtons.vue";
    export default {
      components: {
        HeaderTitle,
        SearchPanel,
        ToDoList,
        AddFormsTask,
        FilterButtons
      },
      data(){
        return {
          todos: [
            {id: 1, text: 'Learn Vue.js', important: true, done: false}, 
            {id: 2, text: "Drink Coffee", important: false, done: true},
            {id: 3, text: "Drink Water", important: true, done: false}
          ],
          status: 'all',
          searchPanel: ''
        }
      },
      computed: {
        foundTasks(){
          return this.todos.filter((todo) => {
            todo.text.toLowerCase().includes(this.searchValue.toLowerCase())
          })
        },
        filterTasks(){
          if(this.status === 'all'){
            return this.todos
          } else if (this.status === 'done') {
            return this.todos.filter((todo) => todo.done)
          } else {
            return this.todos.filter((todo) => todo.important)
          }
        }
      },
      methods: {
        onDone(id) {
          if(!id){
            throw "Is not found"
          } else {
            toggle(this.todos, id)
            // let idx = this.todos.findIndex(item => item.id === id)
            // this.todos[idx].done = !this.todos[idx].done
          }
      },
      addTask(val){
        let newTask = {
          id: this.todos.length + 1,
          text: val
        }
        this.todos.push(newTask)
      },
      onChangeStatus(value){
        this.status = value
      },
        onImportant(id) {
          if(!id){
            throw "Is not found"
          } else {
            let idx = this.todos.findIndex(item => item.id === id)
            this.todos[idx].important = !this.todos[idx].important
          }
        },
        onDelete(id){
          let idx = this.todos.findIndex(item => item.id === id);
          this.todos.splice(idx, 1)
        },
      }
    }
</script>
