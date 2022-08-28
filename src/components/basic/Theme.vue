<template>
    <div class="theme-wrapper" :class="computedClass" :style="computedStyle">
        <div class="theme-bg-mask bg-white/10 dark:bg-black/50">
            <slot></slot>
        </div>
    </div>
</template>

<script setup>
import { defineProps, computed } from 'vue';
const props = defineProps({
    theme: {
        type: String,
        default: 'light',
        required: false,
        validator(value) {
            return ['light', 'dark'].includes(value)
        }
    },
    backgroundColor: {
        type: String,
        required: false
    },
    backgroundImage: {
        type: String,
        required: false
    }
})

const computedClass = computed(() => {
    return {
        'bg-gray-200': !(props.backgroundColor || props.backgroundImage),
        'dark': props.theme === 'dark'
    }
})

const computedStyle = computed(() => {
    return {
        'background-color': props.backgroundColor,
        'background-image': `url(${props.backgroundImage})`
    }
})

</script>

<style>
.theme-wrapper {
    @apply w-full h-full;
    @apply bg-fixed bg-cover bg-center;
}

.theme-bg-mask {
    @apply w-full h-full;
    @apply backdrop-blur;
}
</style>