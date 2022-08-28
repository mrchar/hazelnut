<template>
    <div class="p-2 bg-white rounded-2xl shadow flex gap-x-2 items-center">
        <div>
            <input type="checkbox" v-model="todo.finished">
        </div>
        <div>
            <div> {{ todo.summary }}</div>
            <div class="text-sm text-gray-500">{{ todo.description }}</div>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from "vue"


const props = defineProps({
    todo: {
        type: Object
    }
})
</script>