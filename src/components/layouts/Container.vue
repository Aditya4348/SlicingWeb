<script setup>
const props = defineProps({
    class: {
        type: String,
        default: ''
    }
})
</script>


<template>
    <div :class="['container mx-auto px-4', props.class]">
        <slot></slot>
    </div>
</template>