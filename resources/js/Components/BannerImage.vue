<script setup>
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
        class="w-full md:w-[950px] md:h-screen px-4 sm:pr-12 flex flex-col place-items-center justify-start sm:justify-center h-2/5 transition-all duration-200 ease-in-out"
        :class="{
            ' ': isScrolling,
            '': !isScrolling,
        }"
    >
        <img src="images/Pair-programming.png" class="" alt="Image" />
    </div>
</template>
