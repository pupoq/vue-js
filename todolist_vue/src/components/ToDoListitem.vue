<template>
        <div>     
            <li class="todo_item" :class="{important_task: important, done }">
                {{text}}
                <button v-on:click="important = !important">Important</button>
                <button @click="onDone">Done</button>
                <button>Delete</button>
            </li>
        </div>
</template>

<script>
export default {
    props: {
        text: {type: String, default: "", required: true}
    },
    data() {
        return {
            important: false,
            done: true
        }
    },
    methods: {
        onDone(){
            this.done = !this.done
            console.log(this)
        }
    }
}
</script>

<style scoped>
    .todo_item{
        font-family: 'Courier New', Courier, monospace;
        padding: 10px;
        border: 1px solid rgb(197, 197, 197);
        margin-top: 10px;
        border-radius: 5px
    }

    .important_task {
        font-weight: bold;
        color: slateblue
    }

    .done {
        text-decoration: line-through
    }

    button{
        margin-top: 10px
    }
</style>

