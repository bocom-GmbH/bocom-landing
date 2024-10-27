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
                    <div class="step-title">{{ step.title }}</div>
                    <img :src="'/public/img/' + step.logo" alt="Step Icon" class="step-logo" />
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
    background-image: url('/public/img/steps-background.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: 100%;
    min-width: 80%;
}

.steps-container {
    width: 1200px;
    margin: 0;
    text-align: center;
}

.steps-title {
    font-size: var(--h1-lg-size);
    margin-bottom: 5rem;
    color: white;
    text-transform: uppercase;
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
    background-color: var(--primary-color);
    padding: 40px;
    border-radius: 15px;
    /*  flex: 0 0 10%; */
    width: -webkit-fill-available;
    max-width: 350px;
    text-align: center;
    position: relative;
}

.step-logo {
    width: 60px;
    height: auto;
    margin-bottom: 10px;
}

.step-title {
    font-size: var(--h2-lg-size);
    margin-bottom: 10px;
    color: white;
    margin-top: 0;
    position: absolute;
    top: -40px;
    left: 50%;
    transform: translateX(-50%);
    background-color: var(--primary-color);
    padding: 5px 15px;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}

.step-subtitle {
    font-size: var(--h3-lg-size);
    color: white;
    margin-bottom: 10px;
}

.step-description {
    font-size: var(--h3-lg-size);
    color: white;
}

@media (max-width: 2100px) {
    .step-card {
        max-width: 300px;
        padding: 30px;
    }
    .steps-title {
        font-size: var(--h2-lg-size);
    }
    .step-subtitle {
        font-size: var(--h3-md-size);
    }
    .step-description {
        font-size: var(--h3-md-size);
    }
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
