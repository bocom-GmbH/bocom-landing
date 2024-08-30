<script setup lang="ts">
import { ref } from 'vue'
import '../assets/main.css'

const isHovered = ref(false)
const isFocused = ref(false)

function handleMouseEnter() {
    isHovered.value = true
}

function handleMouseLeave() {
    isHovered.value = false
}
</script>

<template>
    <button
        :class="['call-to-action-button', { isHovered: isHovered, isFocused: isFocused }]"
        @mouseenter="handleMouseEnter"
        @mouseleave="handleMouseLeave"
    >
        <slot></slot>
    </button>
</template>

<style scoped>
.call-to-action-button {
    padding: 10px 20px;
    border: none;
    background-color: var(--primary-color);
    color: var(--primary-button-text);
    font-size: 1.2rem;
    font-weight: bold;
    transition: all 0.3s ease-in-out;
    border-radius: 25px;
    cursor: pointer;
}
.isHovered {
    background-color: var(--primary-button-color-hover);
}

@media (max-width: 768px) {
    .call-to-action-button {
        font-size: 1.1rem;
        /* padding: 8px 16px; */
    }
}

@media (max-width: 480px) {
    .call-to-action-button {
        font-size: 1rem;
        /*  padding: 6px 12px; */
    }
}
</style>
