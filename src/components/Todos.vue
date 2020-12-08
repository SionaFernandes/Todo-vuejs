<template>
<div>
    <h2 class="title">My todolist</h2>
    <ul>
        <li v-bind:key="todo.id" v-for="todo in todos">
            <Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)" />
        </li>
    </ul>
</div>
</template>

<script>
import Todo from './Todo';
export default {
    name: 'Todos',
    components: {
        Todo
    },
    props: [
        "todos"
    ]
}
</script>

<style scoped>
.title{
  font-size: 3rem;
}
ul{
  list-style: none;
  padding: 0;
  width:60%;
  margin: 0 auto;
}
li{
  padding:10px;
  margin:20px 0;
  background-color: rgb(210 206 206);
}

</style>
