<template>
    <div>
        <div>
            <input class=input type=text v-model="input"/>
            <button @click="$emit('addNewTask', input)">Button</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            input: ''
        }
    },
    emits: ['addNewTask'],
    // props: {
    //     addTask: Function
    // },
}
</script>>