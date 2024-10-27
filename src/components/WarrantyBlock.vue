<script setup lang="ts">
import CallToActionButton from './CallToActionButton.vue'
const props = defineProps<{
    top: string
    bottom: string
}>()
</script>

<template>
    <div class="vector_warranty">
        <div class="warranty-block">
            <div class="text-section_warranty">
                <p v-html="top" class="top-text"></p>
                <div class="bottom-text-wrapper">
                    <p class="bottom-text">{{ bottom }}</p>
                    <!-- <img src="/public/img/underline.svg" alt="vector_warranty" class="underline" /> -->
                </div>
            </div>
            <div class="icon-section_warranty">
                <img
                    src="/public/img/verified-check-svgrepo-com.svg"
                    alt="Check Icon"
                    class="icon_warranty"
                />
            </div>
        </div>
        <div>
            <CallToActionButton>RÜCKRUF ANFORDERN</CallToActionButton>
        </div>
    </div>
</template>

<style>
.vector_warranty {
    /* background-image: url('/public/img/wawe.svg'); */
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
    width: 100%;
    padding: 16rem 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

@media (min-width: 1024px) {
    .vector_warranty {
        /*  background-image: none; */
    }
}

.warranty-block {
    display: flex;
    flex-direction: row;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    /* gap: 10px; */
    position: relative;
    margin-bottom: 3rem;
}

.text-section_warranty {
    text-transform: uppercase;
    z-index: 2;
    font-size: var(--subtitle-size);
    color: var(--primary-color);
}

.highlight {
    color: var(--orange-color);
    font-weight: bold;
    text-decoration: underline;
}

.bottom-text-wrapper {
    display: flex;
    justify-content: center;
    width: fit-content;
    position: relative;
}

.bottom-text {
    font-size: var(--h2-lg-size);
    width: fit-content;
    margin-bottom: 0 !important;
}
.top-text {
    font-size: var(--h2-lg-size);
    margin-bottom: 0;
}

.underline {
    width: 100%;
    position: absolute;
    left: 0;
    bottom: -15px;
}

.icon_warranty {
    z-index: 2;
    width: 300px;
    height: auto;
}

@media (max-width: 2100px) {
    .warranty-block {
        max-width: 1200px;
    }
    .bottom-text {
        font-size: var(--h2-md-size);
    }
    .top-text {
        font-size: var(--h2-md-size);
    }
}

@media (max-width: 768px) {
    .warranty-block {
        flex-direction: column;
        align-items: center;
        text-align: center;
        padding: 20px;
        margin-top: 0;
        margin-bottom: 3rem;
    }

    .bottom-text-wrapper {
        align-items: center;
        margin: 0 auto;
    }

    .text-section_warranty {
        margin-bottom: 20px;
    }

    .icon_warranty {
        width: 80px;
    }
}
</style>
