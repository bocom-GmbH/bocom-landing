<script setup lang="ts">
import CallToActionButton from '@/components/CallToActionButton.vue'

const props = defineProps<{
    title: string
    items: Array<{ title: string; description: string }>
}>()
</script>

<template>
    <div class="list-container">
        <h2 class="list-title">{{ title }}</h2>
        <div class="list-item" v-for="(item, index) in props.items" :key="index">
            <!-- <img :src="'/img/negative-sign-inside-circle.svg'" alt="Icon" class="icon" /> -->
            <div class="text-content">
                <h3 class="item-title">{{ item.title }}</h3>
                <p class="item-description">{{ item.description }}</p>
            </div>
        </div>
        <CallToActionButton>RÜCKRUF ANFORDERN</CallToActionButton>
    </div>
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
    color: var(--primary-color);
}

.list-title {
    text-transform: uppercase;
    text-align: center;
    font-size: var(--h2-lg-size);
    margin-bottom: 20px;
    font-weight: bold;
}

.list-item {
    display: flex;
    align-items: start;
    margin-bottom: 20px;
    margin-left: 20px;
}

.icon {
    width: 40px;
    height: 40px;
    margin-right: 15px;
    margin-top: 20px;
}

.text-content {
    flex: 1;
}

.item-title {
    text-align: left;
    font-size: var(--h3-lg-size);
    font-weight: bold;
    margin-bottom: 5px;
}

.item-description {
    text-align: left;
    font-size: var(--h3-lg-size);
    color: var(--primary-color);
}

@media (max-width: 2100px) {
    .list-container {
        max-width: 1200px;
    }
    .list-title {
        font-size: var(--h2-md-size);
    }
    .item-title {
        font-size: var(--h3-md-size);
    }
    .item-description {
        font-size: var(--h3-md-size);
    }
}

@media (max-width: 768px) {
    .list-container {
        padding: 16px;
    }

    .list-item {
        flex-direction: column;
        align-items: center;
        text-align: center;
        margin-left: 0;
    }

    .icon {
        margin: 0;
    }

    .text-content {
        text-align: center;
    }

    .item-title {
        margin-top: 10px;
        margin-bottom: 0;
        font-size: 1.3rem;
    }

    .item-description {
        font-size: 1rem;
    }
}
</style>
