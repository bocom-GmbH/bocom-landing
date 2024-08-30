<script setup lang="ts">
import CallToActionButton from './CallToActionButton.vue'
const props = defineProps<{
    clients: Array<{
        image: string
        name: string
        description: string
        logo: string
        link_url: string
        link: string
    }>
}>()
</script>

<template>
    <div class="container">
        <h2 class="title">Unsere Kunden bringen es auf den Punkt</h2>
        <div class="clients-container">
            <div class="client-card" v-for="(client, index) in clients" :key="index">
                <img :src="'/public/img/' + client.image" alt="Kunde" class="client-image" />
                <div class="card-body">
                    <h3 class="client-name">{{ client.name }}</h3>
                    <h4 class="client-description">{{ client.description }}</h4>
                    <img
                        :src="'/public/img/' + client.logo"
                        alt="Kunden Logo"
                        class="client-logo"
                    />
                    <a :href="client.link_url" class="link-button"> {{ client.link }} </a>
                </div>
            </div>
        </div>
        <CallToActionButton>RÜCKRUF ANFORDERN</CallToActionButton>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 7rem;
    margin-bottom: 7rem;
}

.title {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 3rem;
}

.clients-container {
    width: 100%;
    display: flex;
    overflow-x: scroll;
    gap: 20px;
    scroll-behavior: smooth;
    margin-bottom: 3rem;
}

.client-card {
    background-color: var(--secondary-color);
    border-radius: 15px;
    min-width: 300px;
    max-width: 300px;
}

.card-body {
    padding: 10px;
    display: flex;
    flex-direction: column;
}

.client-name {
    text-align: center;
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: var(--primary-color);
}

.client-description {
    text-align: center;
}

.client-image {
    object-fit: cover;
    height: 250px;
    width: 300px;
    border-top-left-radius: 15px;
    border-top-right-radius: 15px;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
}

.client-logo {
    margin: 0 auto;
    width: 70%;
    mix-blend-mode: darken;
}

.link-button {
    margin: 0 auto;
    font-size: 1.2rem;
    color: var(--primary-color);
    padding: 10px;
    text-decoration: none;
}

.client-card:first-child {
    margin-left: 25%;
}

.client-card:last-child {
    margin-right: 25%;
}

.step-description {
    font-size: 1rem;
    color: #333;
}

@media (max-width: 768px) {
    .container {
        min-width: 95%;
        margin-top: 3rem;
        margin-bottom: 3rem;
    }

    .clients-container {
        max-width: 100%;
    }

    .client-image {
        width: 100%;
    }

    .client-card:first-child {
        margin-left: 2rem;
    }

    .client-card:last-child {
        margin-right: 2rem;
    }

    .client-card {
        /* flex: 0 0 70%; */
        min-width: 280px;
        max-width: 280px;
    }
}
</style>
