<template>
    <div class="todo-item" v-bind:class="{'is-complete':newTodo.completed}">
        
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{newTodo.title}}</p>
    </div>
</template>
<script>
export default {
    name:"TodoItem",
    props:["todo"],
    data(){
        return {
            newTodo : {}
        }
    },
    methods: {
        markComplete() {


          this.newTodo.completed = ! this.newTodo.completed;
        }
    },
    mounted(){
        this.newTodo = this.todo;
    }
}
</script>
<style scoped>
    .todo-item{
        background-color: #f4f4f4;
        border-bottom: 1px dotted #ccc;
        padding: 10px;
    }
    .is-complete{
        text-decoration: line-through;
    }
    .del{
        background: #fff000;
        color:#fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;


    }

</style>