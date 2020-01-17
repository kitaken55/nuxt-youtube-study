<template>
    <div>
        <ul>
            <li v-for="todo in todos" v-bind:key="todo.text">
                <input type="checkbox" :checked="todo.done" @change="toggle(todo)">
                <span :class="{ done: todo.done }">{{ todo.text }}</span>
            </li>
        </ul>
        <input placeholder="タスクを追加" @keyup.enter="addTodo">
    </div>
</template>

<script>
import { mapMutations } from 'vuex'
export default {
    computed: {
        todos() {
            return this.$store.state.todos.list
        }
    },
    methods: {
        addTodo(e) {
            this.$store.commit('todos/add', e.target.value)
        },
        ...mapMutations({
              toggle: 'todos/toggle'
        }),
        // toggle(todo) {
        //     this.$store.commit('todos/toggle', todo)
        // }
    }

}
</script>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>