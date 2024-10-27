<script lang="ts" setup></script>

<template>
    <div class="footer">
        <div class="footer-content">
            <img
                style="max-width: 180px; mix-blend-mode: color-burn"
                src="/img/bocom_logo.png"
                alt="logo"
            />
        </div>
        <div class="footer-content">
            <div>bocom GmbH | Zum alten Ziegelofen 150G | 2485 Wimpassing an der Leitha</div>
            <div>Kontakt/Impressum ©2022-2024 | AGB</div>
        </div>
    </div>
</template>

<style scoped>
.footer > div {
    margin: 0 10px;
    font-size: 1.2rem;
    color: white;
    padding: 1rem;
}

.footer {
    background-color: var(--primary-color);
    padding: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.footer-content {
    display: flex;
    flex-direction: row;
    gap: 40px;
}
</style>
