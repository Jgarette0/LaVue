<!-- resources/js/Pages/Home.vue -->
<script setup>
import MainLayout from "@/Layout/MainLayout.vue";
import Title from "@/Components/Title.vue";
const pageTitle = " Welcome";
</script>

<template>
    <Title :title="`${pageTitle}`" />
    <MainLayout>
        <div class="h-screen"></div>
    </MainLayout>
</template>
