<script setup lang="ts">
import CallToActionButton from './CallToActionButton.vue'
const props = defineProps<{
    steps: Array<{ logo: string; title: string; subtitle: string; description: string }>
}>()
</script>

<template>
    <div class="container">
        <div class="steps-container">
            <h2 class="steps-title">So legen Sie los!</h2>
            <div class="steps-wrapper">
                <div class="step-card" v-for="(step, index) in steps" :key="index">
                    <img :src="'/public/img/' + step.logo" alt="Step Icon" class="step-logo" />
                    <h3 class="step-title">{{ step.title }}</h3>
                    <h4 class="step-subtitle">{{ step.subtitle }}</h4>
                    <p class="step-description">{{ step.description }}</p>
                </div>
            </div>
            <CallToActionButton>RÜCKRUF ANFORDERN</CallToActionButton>
        </div>
    </div>
</template>

<style scoped>
.container {
    padding-top: 7rem;
    padding-bottom: 7rem;
    background-image: url('/public/img/test.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: 100%;
    min-width: 80%;
}

.steps-container {
    /* max-width: 1200px; */
    margin: 0;
    text-align: center;
}

.steps-title {
    font-size: 2rem;
    margin-bottom: 3rem;
}

.steps-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 20px;
    /* padding-left: 35rem;
    padding-right: 35rem; */
    margin-bottom: 3rem;
}

.step-card {
    background-color: var(--secondary-color);
    padding: 20px;
    border-radius: 15px;
    /*  flex: 0 0 10%; */
    width: -webkit-fill-available;
    max-width: 280px;
    text-align: center;
}

.step-logo {
    width: 60px;
    height: auto;
    margin-bottom: 10px;
}

.step-title {
    font-size: 1.5rem;
    margin-bottom: 10px;
    color: #5e3c6d;
}

.step-subtitle {
    font-size: 1.2rem;
    color: black;
    margin-bottom: 10px;
}

.step-description {
    font-size: 1rem;
    color: #333;
}

@media (max-width: 768px) {
    .container {
        min-width: 95%;
    }

    .steps-wrapper {
        width: auto;
        grid-template-columns: 1fr;
        gap: 20px;
        padding-left: 0.5rem;
        padding-right: 0.5rem;
    }

    .step-card {
        /* flex: 0 0 70%; */
        width: -webkit-fill-available;
        max-width: 100%;
    }

    .cta-button {
        width: 100%;
    }
}
</style>
