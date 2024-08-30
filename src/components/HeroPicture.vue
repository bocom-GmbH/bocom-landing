<script setup lang="ts">
import CallToActionButton from './CallToActionButton.vue'

const props = defineProps<{
    title: string
    description: string
}>()
</script>

<template>
    <div class="hero-container">
        <img src="/img/test.jpg" alt="Hero Image" class="hero-image" />
        <div class="hero-content">
            <h1 class="hero-title">{{ props.title }}</h1>
            <p class="hero-subtitle">{{ props.description }}</p>
            <CallToActionButton>JETZT ANRUFEN</CallToActionButton>
        </div>
    </div>
</template>

<style scoped>
/* Hero container */
.hero-container {
    position: relative;
    padding-top: 100px;
    height: 70vh; /* 70% of the viewport height */
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden; /* Ensures content stays within the container */
}

/* Hero image with darkening filter */
.hero-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    filter: brightness(40%); /* Darkening the image by 70% */
    z-index: 1;
}

/* Content centered in the hero section */
.hero-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    z-index: 2;
    text-align: center;
    color: white;
    padding: 20px;
}

/* Title styling */
.hero-title {
    font-size: 4rem;
    margin-bottom: 0.6rem;
}

/* Subtitle styling */
.hero-subtitle {
    font-size: 2rem;
    margin-bottom: 1.6rem;
    max-width: 600px;
}

/* Responsive design for smaller screens */
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
