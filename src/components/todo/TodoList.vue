<template>
    <div class="w-full h-full p-2 flex flex-col gap-2">
        <div class="w-full h-full flex flex-col gap-2">
            <div class="h-16" v-for="(todo, index) in todos" :key="index">
                <TodoItem :todo="todo">
                </TodoItem>
            </div>
        </div>
        <div class="w-full h-16 text-center bg-white rounded-2xl shadow">
            <button class="w-full h-full align-middle">添加</button>
        </div>
    </div>
    <div class="fixed top-0 w-full h-full">
        <TodoForm></TodoForm>
    </div>
</template>

<script setup>
import { ref } from "vue"
import TodoItem from "@/components/todo/TodoItem.vue"
import TodoForm from "@/components/todo/TodoForm.vue"

const todos = ref([
    {
        summary: "第一件事",
        description: "描述可以不写",
        finished: false
    },
    {
        summary: "第二件事",
        description: "描述可以不写",
        finished: true
    }
])
</script>