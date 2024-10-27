<script setup lang="ts">
import CallToActionButton from './CallToActionButton.vue'
const props = defineProps<{
    toggle: () => void
}>()
</script>

<template>
    <div @click="toggle" class="popup">
        <div @click.stop class="popup-inner">
            <div class="header">
                <button @click="toggle" class="popup-close">X</button>
            </div>
            <div class="body">
                <img
                    src="/public/img/bocom_logo_mit_Claim_darunter_Marketing_für_Apotheken_tme.png"
                    alt=""
                    style="max-width: 300px"
                />
                <div>
                    <div class="form">
                        <div>Kostenlose Erstberatung Anfordern</div>
                        <input
                            type="
                        "
                            placeholder="Name*"
                        />
                        <input
                            placeholder="Telefonnummer*"
                            type="
                        "
                        />
                        <CallToActionButton>RÜCKRUF ANFORDERN</CallToActionButton>
                    </div>
                </div>
            </div>
            <!-- <slot /> -->
        </div>
    </div>
</template>

<style scoped>
.popup {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 99;
    background-color: rgba(0, 0, 0, 0.2);
    display: flex;
    align-items: center;
}
.popup-inner {
    margin: auto;
    background-color: white;
    padding: 32px;
    max-width: 800px; /* Adjust the size as needed */
    width: 100%;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Optional for better visibility */
    border-radius: 8px;
}

.header {
    display: flex;
    justify-content: end;
}

.body {
    padding: 3rem 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-right: 2rem;
    margin-left: 3rem;
    align-items: center;
}

.form > :first-child {
    font-size: 1.5rem;
}

input {
    padding: 1rem;
    border: 1px solid black;
    border-radius: 30px;
    width: 300px;
}
</style>
