<script lang="ts" setup>
const props = defineProps<{
    links: Array<{ text: string; link: string }>
    copyright: string
}>()
</script>

<template>
    <div class="footer">
        <div class="footer-content">
            <div>Impressum</div>
            <div>AGB</div>
        </div>
    </div>
</template>

<style scoped>
.footer > div {
    margin: 0 10px;
    font-size: 1.2rem;
    color: grey;
    padding: 1rem;
}

.footer {
    background-color: var(--secondary-color);
    padding: 10px;
}

.footer-content {
    display: flex;
    flex-direction: row;
    gap: 10px;
}
</style>
