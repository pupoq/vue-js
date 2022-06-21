<template>
    <div>
        <div>
            <input v-bind:type="passwordVisible?'text':'password'" name="" id="inp"/>
            <button v-on:click="passwordVisible = !passwordVisible">Button</button>
        </div>
    </div>
</template>