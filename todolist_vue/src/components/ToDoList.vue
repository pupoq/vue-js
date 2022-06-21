<template>
    <ul>
        <ToDoListitem v-for='item in todos' :key="item.id" :text='item.text' />
    </ul>
</template>

<script>
import ToDoListitem from "./ToDoListitem.vue"

export default {
    props: {
        todos: Array
    },
    components: { ToDoListitem }
}
</script>
