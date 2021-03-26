<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}</p>
    </div>
</template>
<script>
export default {
    name:"TodoItem",
    props:{
        todo: {
            type: Object,
            required:true
        }
    },
    methods: {
        markComplete() {
            this.todo.completed=!this.todo.completed;
        }
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