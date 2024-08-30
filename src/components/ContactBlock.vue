<script setup lang="ts">
import CallToActionButton from '@/components/CallToActionButton.vue'
const props = defineProps({
    title: String,
    inputs: Array<String>
})
</script>

<template>
    <div class="section">
        <div class="form-container">
            <img
                src="/public/img/bocom_logo_mit_Claim_darunter_Marketing_für_Apotheken_tme.png"
                alt="Logo"
                class="logo"
            />
            <div class="form-content">
                <h2 class="form-title">{{ title }}</h2>
                <div class="form-group" v-for="(input, index) in inputs" :key="index">
                    <input :placeholder="props.inputs[index]" type="text" class="form-input" />
                </div>
                <CallToActionButton style="width: 100%">RÜCKRUF ANFORDERN</CallToActionButton>
            </div>
        </div>
    </div>
</template>

<style scoped>
.section {
    display: flex;
    align-items: center;
    max-width: 800px;
    margin: 0 auto;
    padding: 10rem 20px;
}

.form-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: var(--secondary-color);
    border-radius: 15px;
    padding: 20px;
    width: 100%;
    max-width: 800px;
    /* box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); */
}

.logo {
    max-width: 300px;
    height: auto;
}

.form-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px;
    flex: 1;
    margin-left: 20px;
    max-width: 400px;
}

.form-title {
    font-size: 1.8rem;
    margin-bottom: 10px;
    font-weight: bold;
    color: #333;
}

.form-group {
    width: 100%;
    display: flex;
    flex-direction: column;
}

.form-input {
    padding: 10px;
    border-radius: 20px;
    border: 1px solid #ccc;
    font-size: 1rem;
    transition:
        box-shadow 0.3s ease,
        border-color 0.3s ease;
}

.form-input:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 0 2px var(--primary-color);
}

@media (max-width: 768px) {
    .section {
        padding: 5rem 0.5rem;
    }

    .form-container {
        flex-direction: column;
        align-items: center;
        text-align: center;
    }

    .logo {
        max-width: 200px;
        height: auto;
        margin-bottom: 20px;
    }

    .form-content {
        margin-left: 0;
    }
}
</style>
