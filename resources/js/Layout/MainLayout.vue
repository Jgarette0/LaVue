<script setup>
import Header from "./Header.vue";
import Footer from "./Footer.vue";
</script>

<template>
    <div class="flex flex-col w-screen border">
        <Header />
        <main>
            <div class="flex flex-col p-4 bg-secondary">
                <slot></slot>
            </div>
        </main>
        <Footer />
    </div>
</template>
