<script setup lang="ts">
import fehler from '../../public/img/fehler.svg'
import CallToActionButton from '@/components/CallToActionButton.vue'
const props = defineProps<{
    title: string
    first: Array<{ title: string; description: string }>
    secound: Array<{ title: string; description: string }>
}>()
</script>

<template>
    <div class="list-container">
        <h2 class="list-title">{{ title }}</h2>
        <div class="first-box-container">
            <div class="first-boxes" v-for="(box, index) in first" :key="index">
                <h3>{{ box.title }}</h3>
                <p>{{ box.description }}</p>
            </div>
        </div>
        <div class="secound-box-container">
            <div class="secound-boxes" v-for="(box, index) in secound" :key="index">
                <img src="../../public/img/fehler.svg" alt="fehler" />
                <div>
                    <h3>{{ box.title }}</h3>
                    <p>{{ box.description }}</p>
                </div>
            </div>
        </div>
        <CallToActionButton>RÜCKRUF ANFORDERN</CallToActionButton>
    </div>
    <!-- {{ secound }} -->
</template>

<style scoped>
.list-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 1200px !important;
    margin: 0 auto;
    padding-top: 5rem;
    padding-bottom: 3rem;
}

.list-title {
    color: var(--primary-color);
    text-transform: uppercase;
    text-align: center;
    font-size: var(--h2-lg-size);
    margin-bottom: 50px;
    font-weight: bold;
}

.first-box-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
    gap: 20px;
    margin-bottom: 20px;
}

.first-boxes {
    background-color: var(--primary-color);
    color: white;
    align-items: start;
    padding: 25px;
    border-radius: 15px;
}

.secound-box-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 100%;
    gap: 20px;
    margin-bottom: 3rem;
}

.secound-boxes {
    background-color: var(--primary-color);
    color: white;
    align-items: start;
    padding: 25px;
    border-radius: 15px;
    display: flex;
    align-items: center;
    gap: 25px;
}

h3 {
    font-size: var(--h3-lg-size);
    margin-bottom: 30px;
}

p {
    font-size: var(--description-size);
    line-height: 1.5;
}
</style>
