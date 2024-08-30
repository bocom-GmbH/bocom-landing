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
</script>

<template>
    <main>
        <NavigationBar :logo="content.navbar.logo" :links="content.navbar.links" />
        <HeroPicture
            :title="content.heroPicture.title"
            :description="content.heroPicture.desctiption"
        />
        <ArgumentList :title="content.list.title" :items="content.list.items" />
        <ContactBlock :title="content.dialog.title" :inputs="content.dialog.inputs" />
        <WarrantyBlock :top="content.warranty.top" :bottom="content.warranty.bottom" />
        <StepsBlock :steps="content.steps" />
        <ScrollableView :clients="content.clients" />
        <FooterComponent />
    </main>
</template>

<style scoped></style>
