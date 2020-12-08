<template>
<div>
    <form @submit="addTodo">
        <input type="text" v-model="title" name="title">
        <button class="btn" type="submit">Add</button>
    </form>
</div>
</template>

<script>
import {
    v4 as uuidv4
} from 'uuid';

export default {
    name: 'AddTodo',
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodoObj = {
                id: uuidv4(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodoObj);
            this.title = '';
            let classes = ['tasks__item__toggle'];
            classes.push('tasks__item__toggle--completed');
        }
    }
}
</script>

<style scoped >
input[type=text] {
    padding: 12px 20px;
    margin: 8px;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}

.btn {
    padding: 15px;
    border: none;
}

.btn:hover {
    cursor: pointer;
}
</style>
