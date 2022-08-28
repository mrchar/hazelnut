<template>
    <div class="card-wrapper" :class="{ 'inline-block': !props.block, 'block': props.block }">
        <slot></slot>
    </div>
</template>

<script setup>
import { defineProps } from "vue"
const props = defineProps({
    block: {
        type: Boolean,
        default: true
    }
})
</script>

<style scoped>
.card-wrapper {
    @apply p-2 rounded shadow;
    @apply bg-white;
}
</style>