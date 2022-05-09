<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem />
        </div>
    </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
    name: "TodosComponent",
    props: ["todos"],
    components: { TodoItem }
}
</script>

<style scoped>

</style>
