<script setup lang="ts">
import NavigationBar from '@/components/NavigationBar.vue'
import HeroPicture from '@/components/HeroPicture.vue'
import ArgumentList from '@/components/ArgumentList.vue'
import ContactBlock from '@/components/ContactBlock.vue'

import content from '../../content.json'
import WarrantyBlock from '@/components/WarrantyBlock.vue'
import StepsBlock from '@/components/StepsBlock.vue'
import ScrollableView from '@/components/ScrollableView.vue'
import FooterComponent from '@/components/FooterComponent.vue'
import PopUp from '@/components/PopUp.vue'
import ArgumentGird from '@/components/ArgumentGrid.vue'

import { provide, ref } from 'vue'

const isOpen = ref(false)

provide('isOpen', isOpen)

const toggle = () => {
    isOpen.value = !isOpen.value
}
</script>

<template>
    <Transition>
        <PopUp
            :toggle="
                () => {
                    toggle()
                }
            "
            v-if="isOpen"
        ></PopUp>
    </Transition>
    <main>
        <NavigationBar :logo="content.navbar.logo" :links="content.navbar.links" />
        <HeroPicture
            :title="content.heroPicture.title"
            :description="content.heroPicture.desctiption"
        />

        <ArgumentGird
            :title="content.list2.title"
            :first="content.list2.first"
            :secound="content.list2.secound"
        />
        <ArgumentList :title="content.list.title" :items="content.list.items" />
        <!-- <ContactBlock :title="content.dialog.title" :inputs="content.dialog.inputs" /> -->
        <WarrantyBlock :top="content.warranty.top" :bottom="content.warranty.bottom" />
        <StepsBlock :steps="content.steps" />
        <ScrollableView :clients="content.clients" />
        <FooterComponent />
    </main>
</template>

<style scoped>
.v-enter-active,
.v-leave-active {
    transition: all 0.2s ease-in-out;
}

.v-enter-from,
.v-leave-to {
    transform: translateY(-10px);
    opacity: 0;
}
</style>
