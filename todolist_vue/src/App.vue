
<template>
  <div>
    <HeaderTitle />
    <SearchPanel />

    <ToDoList :todos='todos' :onToggleDone="onDone" :onToggleImportant='onImportant' :id='id' @handleDelete='onDelete'/>
    <AddFormsTask />
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
            {id: 1, text: 'Learn Vue.js', important: true, done: false}, 
            {id: 2, text: "Drink Coffee", important: false, done: true}
          ],
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
        onImportant(id) {
          if(!id){
            throw "Is not found"
          } else {
            let idx = this.todos.findIndex(item => item.id === id)
            this.todos[idx].important = !this.todos[idx].important
          }
        },
        onDelete(id) {
          console.log('delete', id)
          let idx = this.todos.findIndex(item => item.id === id);
          this.todos.splice(idx, 1)
        }
      }
    }
</script>
