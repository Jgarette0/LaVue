<script setup>
import { Button } from "@/Components/ui/button";
import { ref, onMounted, onUnmounted } from "vue";

const isScrolling = ref(false);

const updateScroll = () => {
    isScrolling.value = window.scrollY > 0;
};

onMounted(() => {
    window.addEventListener("scroll", updateScroll);

    onUnmounted(() => {
        window.removeEventListener("scroll", updateScroll);
    });
});
</script>

<template>
    <div
        class="flex flex-col place-items-start justify-end sm:justify-center h-2/3 w-full px-4 sm:pl-6 overflow-hidden gap-4 md:gap-0 md:h-screen transition-all duration-300 ease-in-out xl:scale-115 xl:translate-x-20 xl:translate-y-20"
    >
        <div
            class="text-5xl sm:text-7xl md:text-7xl xl:text-[105px] font-extrabold text-foreground opacity-90 transition-all duration-300 ease-in-out"
        >
            Realize Your
            <span
                class="transition-all duration-300 ease-in-out"
                :class="{
                    'text-primary': isScrolling,
                    'text-primary': !isScrolling,
                }"
                >Software</span
            >
            Vision
        </div>
        <div
            class="flex items-center gap-2 flex-row flex-wrap leading-tight md:mt-4"
        >
            <a href="#webdevelopment" class="hover:opacity-80 cursor-pointer"
                >Web Development</a
            >
            <div
                class="w-px h-6 transition-all ease-in-out duration-300"
                :class="{
                    'bg-primary rotate-12': isScrolling,
                    'bg-foreground': !isScrolling,
                }"
            ></div>
            <a href="#mobiledevelopment" class="hover:opacity- cursor-pointer"
                >Mobile Development</a
            >
            <div
                class="w-px h-6 transition-all ease-in-out duration-300"
                :class="{
                    'bg-primary rotate-12': isScrolling,
                    'bg-foreground': !isScrolling,
                }"
            ></div>
            <a href="#projectmanagement" class="hover:opacity-80 cursor-pointer"
                >Project Management</a
            >
        </div>
        <div class="mt-10 w-screen">
            <Button
                class="px-20 sm:px-24 md:px-36 py-5 hover:opacity-85 hidden sm:flex"
                variant="outline"
                >Contact Us</Button
            >
        </div>
    </div>
</template>
