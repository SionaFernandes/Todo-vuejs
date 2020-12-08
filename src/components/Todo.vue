<template>
<div class="todo" v-bind:class="{ 'completed': todo.completed }">
    <p v-on:click="markComplete">{{ todo.title }}</p>
    <button class="btn" @click="$emit('delete-todo', todo.id)">Delete</button>
</div>
</template>

<script>
export default {
    name: 'Todo',
    props: [
        "todo"
    ],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
.todo {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.btn {
    padding: 15px;
    background-color: rgb(143, 6, 6);
    color: #fff;
    border: none;
}

.btn:hover {
    cursor: pointer;
}

.completed {
    text-decoration: line-through;
    
}
</style>
