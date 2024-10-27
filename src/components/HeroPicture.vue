<script setup lang="ts">
import CallToActionButton from './CallToActionButton.vue'

const props = defineProps<{
    title: string
    description: string
}>()
</script>

<template>
    <div class="hero-container">
        <img src="/img/hero.jpg" alt="Hero Image" class="hero-image" />
        <div class="hero-content">
            <h1 class="hero-title">{{ props.title }}</h1>
            <p class="hero-subtitle">{{ props.description }}</p>
            <CallToActionButton>RÜCKRUF ANFORDERN</CallToActionButton>
        </div>
    </div>
</template>

<style scoped>
.hero-container {
    position: relative;
    height: 70vh;
    overflow: hidden;
}

.hero-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 1;
}

.hero-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 2;
    text-align: center;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.hero-title {
    font-size: var(--h1-lg-size);
    margin-bottom: 1rem;
    color: var(--primary-color);
}

.hero-subtitle {
    font-size: var(--h3-lg-size);
    margin-bottom: 3rem;
    max-width: 600px;
    color: var(--primary-color);
}

@media (max-width: 2100px) {
    .hero-title {
        font-size: var(--h1-md-size);
    }

    .hero-subtitle {
        font-size: var(--h3-md-size);
    }
}

@media (max-width: 768px) {
    .hero-title {
        font-size: 2.5rem;
    }

    .hero-subtitle {
        font-size: 1.2rem;
    }
}

@media (max-width: 480px) {
    .hero-title {
        font-size: 2rem;
    }

    .hero-subtitle {
        font-size: 1rem;
    }
}
</style>
