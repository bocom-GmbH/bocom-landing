<script setup lang="ts">
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
                    <img src="/public/img/underline.svg" alt="vector_warranty" class="underline" />
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
    </div>
</template>

<style>
.vector_warranty {
    /* background-image: url('/public/img/vector.svg'); */
    background-position: center center;
    background-size: stretch;
    background-repeat: no-repeat;
}

@media (min-width: 1024px) {
    .vector_warranty {
        background-image: none; /* Eltávolítja a háttérképet nagy kijelzőkön */
    }
}

.warranty-block {
    display: flex;
    flex-direction: row;
    align-items: center;
    max-width: 800px;
    margin: 0 auto;
    margin-top: 3rem;
    margin-bottom: 10rem;
    gap: 20px;
    position: relative;
}

.text-section_warranty {
    z-index: 2;
    font-size: 1.8rem;
}

.highlight {
    color: #d48949;
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
    width: fit-content;
    margin-bottom: 0 !important;
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
