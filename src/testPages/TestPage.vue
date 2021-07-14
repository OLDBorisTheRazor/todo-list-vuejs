<template>
    <div>
        <h2>Test Page</h2>
        <router-link to="/">Home</router-link>
        <hr>
        <div>
            <input type="text" v-model="message">
            <p>v-model test: {{ message }}</p>
            <input type="button" v-on:click="addElem(message)" value="Add Elem">
            <ul><li v-for="(item, index) in arr">{{ item }} <input type="button" value="x" v-on:click="dellItem(index)"></li></ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TestPage",
        data () {
            return {
                message: '',
                arr: [1, 2, 3, 4, 5]
            }
        },
        methods: {
            addElem(q){
                this.arr.push(q)
            },
            dellItem(q){
                this.arr.splice(q, 1)
            }
        }
    }
</script>

<style scoped>
    li {
        list-style: none;
        padding: 0;
        margin: 0 20%;
    }
</style>