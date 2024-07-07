<script setup>
import Header from "./Header.vue";
import Footer from "./Footer.vue";
import Sidebar from "./Sidebar.vue";
</script>

<template>
    <div class="flex flex-col w-screen">
        <Header />
        <Sidebar />
        <main>
            <div class="flex flex-col p-4">
                <slot></slot>
            </div>
        </main>
        <Footer />
    </div>
</template>
