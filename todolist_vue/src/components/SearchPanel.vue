<template>
    <div>
        <new-title />
        <input type="text" name="" id="" placeholder="Search" v-model='inp'>
        {{inp}}
    </div>
</template>

<script>
export default {
    props: ['value'],
    emits: ['searchOneTask'],
    data(){
        return {
            inp: this.props
        }
    },
    methods: {
        show(){
            console.log(this.inp)
        }
    }
}
</script>>