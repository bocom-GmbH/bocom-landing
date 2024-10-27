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
                    <a :href="client.link_url" class="link-button"> {{ client.link }} </a>
                    <h4 class="client-description">{{ client.description }}</h4>
                    <img
                        :src="'/public/img/' + client.logo"
                        alt="Kunden Logo"
                        class="client-logo"
                    />
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
    color: var(--primary-color);
    text-transform: uppercase;
    text-align: center;
    font-size: var(--h2-lg-size);
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
    background-color: var(--primary-color);
    border-radius: 15px;
    min-width: 350px;
    max-width: 350px;
}

.card-body {
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
}

.client-name {
    text-align: center;
    font-size: var(--h3-md-size);
    color: white;
}

.client-description {
    color: white;
    text-align: center;
    font-size: var(--description-size);
}

.client-image {
    object-fit: cover;
    height: 250px;
    width: 350px;
    border-top-left-radius: 15px;
    border-top-right-radius: 15px;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
}

.client-logo {
    margin: 0 auto;
    width: 70%;
    mix-blend-mode: none;
}

.link-button {
    margin: 0 auto;
    font-size: var(--description-size);
    color: white;

    text-decoration: none;
}

.client-card:first-child {
    margin-left: 20%;
}

.client-card:last-child {
    margin-right: 25%;
}

.step-description {
    font-size: 1rem;
    color: white;
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
