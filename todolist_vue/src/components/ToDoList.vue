<template>
    <ul>
        <ToDoListitem v-for='item in todos' 
        :key="item.id" 
        :text='item.text' 
        :done='item.done' 
        :id='item.id'
        :important='item.important' 
        :onDone='onToggleDone'
        :onImportant='onToggleImportant'
        @deleteItem="$emit('handleDelete', item.id)"
        />
    </ul>
</template>

<script>
        import ToDoListitem from "./ToDoListitem.vue"

        export default {
            emits:['handleDelete'],
            props: {
                todos: Array,
                onToggleDone: Function,
                onToggleImportant: Function,
                id:Number
            },
            components: { ToDoListitem }
        }
</script>
