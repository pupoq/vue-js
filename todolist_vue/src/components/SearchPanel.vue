<template>
    <div>
        <new-title />
        <input type="text" name="" id="" placeholder="Search" v-model='inp'>
        {{inp}}
    </div>
</template>

<script>
export default {
    emits: ['searchPanel'],
    data(){
        return {
            inp: ''
        }
    }
}
</script>>