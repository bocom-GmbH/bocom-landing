<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'
import { useRouter } from 'vue-router'
import CallToActionButton from '@/components/CallToActionButton.vue'

const props = defineProps<{
    links: Array<{ text: string; link: string }>
}>()

const router = useRouter()

onMounted(() => {
    window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
})

const isScrolled = ref(false)

function handleScroll() {
    isScrolled.value = window.scrollY > 0
}
</script>

<template>
    <div :class="['navigation-bar', { isScrolled: isScrolled }]">
        <div>
            <img
                :class="['img', { imgIsScrolled: isScrolled }]"
                src="/img/bocom_logo.png"
                alt="logo"
                @click="router.push('/')"
            />
        </div>
        <div class="links">
            <div v-for="link in props.links" :key="link.text">
                <a :href="link.link" class="nav-link">{{ link.text }}</a>
            </div>
            <CallToActionButton>JETZT ANRUFEN</CallToActionButton>
        </div>
    </div>
</template>

<style scoped>
.navigation-bar {
    padding: 0 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 10;
    height: 100px;
    background-color: white;
    transition: all 0.3s ease-in-out;
}

.isScrolled {
    box-shadow: 0 2px 5px grey;
    height: 70px;
}

.img {
    width: 180px;
    transition: width 0.3s ease-in-out;
}
.imgIsScrolled {
    width: 140px;
}

.links {
    gap: 80px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: large;
}

a {
    color: grey;
    text-decoration: none;
}

.nav-link {
    color: grey;
    text-decoration: none;
    position: relative;
    padding-bottom: 5px;
}

.nav-link::after {
    content: '';
    position: absolute;
    left: 50%; /* Start from the center */
    bottom: 0;
    width: 0;
    height: 0;
    background-color: grey;
    border-radius: 5px;
    transition:
       /*  width 0.2s ease-in-out, */ height 0.2s ease-in-out;
    /*  left 0.2s ease-in-out; */
}

.nav-link:hover::after {
    left: 0; /* Move to the left to fill the entire width */
    width: 100%; /* Expand to full width */
    height: 3px; /* Increase height to desired thickness */
}
</style>
