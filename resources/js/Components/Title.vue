<!-- resources/js/Components/Meta.vue -->
<script setup>
import { Head } from "@inertiajs/vue3";

const props = defineProps({
    title: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <Head>
        <title>{{ title }}</title>
    </Head>
</template>
