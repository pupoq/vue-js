<template>
    <div>
        <button :class="{active: value === 'all'}" @click="$emit('change', 'all')">All</button>
        <button :class="{active: value === 'done'}" @click="$emit('change', 'done')">Done</button>
        <button :class="{active: value === 'important'}" @click="$emit('change', 'important')">Important</button>
    </div>
</template>

<script>
export default {
    emits: ['change'],
    props: ['value']
}
</script>>

<style scoped>
    .active {
        background: lightgreen;
        border: 1px solid grey
    }

</style>
