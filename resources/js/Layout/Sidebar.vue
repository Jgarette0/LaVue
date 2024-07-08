<script setup>
import { Link } from "@inertiajs/vue3";
import { onMounted, onUnmounted, ref } from "vue";
import { Button } from "@/Components/ui/button";

const isScrolling = ref(false);
const showTitle = ref(false);
const slideLeft = ref(false);
const updateScroll = () => {
    isScrolling.value = window.scrollY > 0;
};

onMounted(() => {
    window.addEventListener("scroll", updateScroll);

    onUnmounted(() => {
        window.removeEventListener("scroll", updateScroll);
    });
});

const toggle = () => {
    showTitle.value = !showTitle.value;
    setTimeout(() => {
        slideLeft.value = !slideLeft.value;
    }, 200);
};
</script>

<template>
    <main
        class="flex flex-col place-items-center fixed left-0 right-0 top-0 transition-all duration-500 ease-in-out sm:hidden z-20"
    >
        <header
            class="w-full px-2 bg-secondary-accent flex justify-between items-center h-16 top-0 left-0 right-0 fixed"
            :class="{
                'bg-secondary-foreground': isScrolling,
                'bg-secondary-foregroundbg-accent': !isScrolling,
            }"
        >
            <div>
                <img class="h-8" src="images/favic.png" alt="" srcset="" />
            </div>
            <div
                @click="toggle"
                class="cursor-pointer flex flex-col items-center justify-center"
            >
                <svg
                    v-if="!showTitle"
                    xmlns="http://www.w3.org/2000/svg"
                    width="36"
                    height="36"
                    viewBox="0 0 32 32"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    class="lucide lucide-align-right text-primary top-4"
                    :class="{
                        'text-accent': isScrolling,
                        'text-primary': !isScrolling,
                    }"
                >
                    <line x1="21" x2="3" y1="6" y2="6" />
                    <line x1="21" x2="9" y1="12" y2="12" />
                    <line x1="21" x2="7" y1="18" y2="18" />
                </svg>
                <svg
                    v-else
                    xmlns="http://www.w3.org/2000/svg"
                    width="36"
                    height="36"
                    viewBox="0 0 36 36"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    class="lucide lucide-x text-primary top-4"
                    :class="{
                        'text-accent': isScrolling,
                        'text-primary': !isScrolling,
                    }"
                >
                    <path d="M18 6 6 18" />
                    <path d="m6 6 12 12" />
                </svg>
            </div>
        </header>
        <transition
            enter-active-class="transition-opacity duration-300"
            enter-from-class="opacity-0"
            enter-to-class="opacity-100"
            leave-active-class="transition-opacity duration-300"
            leave-from-class="opacity-100"
            leave-to-class="opacity-0"
        >
            <div
                v-show="showTitle"
                class="h-screen w-full bg-secondary-foreground transition-all duration-500 ease-in-out flex flex-col items-start pt-12"
            >
                <div
                    class="h-1/4 w-screen flex flex-row justify-center px-4 gap-3 place-items-end"
                >
                    <div
                        class="font-extrabold font-sans text-2xl text-primary select-none"
                    >
                        GAR TECHNOLOGY
                    </div>
                </div>
                <nav
                    class="w-screen h-screen justify-center gap-4 flex flex-col place-items-start pl-4 py-12"
                >
                    <Link
                        href="/"
                        class="block font-light font-mona text-primary text-3xl hover:opacity-85 transition-all duration-300 delay-100 ease-in-out"
                        :class="slideLeft ? 'translate-x-8' : 'translate-x-72'"
                    >
                        HOME
                    </Link>
                    <Link
                        href="/About"
                        class="block font-light font-mona text-primary text-3xl hover:opacity-85 transition-all duration-300 ease-in-out delay-200"
                        :class="slideLeft ? 'translate-x-8' : 'translate-x-72'"
                    >
                        ABOUT
                    </Link>
                    <Link
                        href="/Services"
                        class="block font-light font-mona text-primary text-3xl hover:opacity-85 transition-all duration-300 ease-in-out delay-300"
                        :class="slideLeft ? 'translate-x-8' : 'translate-x-72'"
                    >
                        SERVICES
                    </Link>
                </nav>
                <div class="h-2/3 w-screen flex flex-col justify-between">
                    <div
                        class="w-screen pl-4 flex place-items-center justify-start transition-all duration-500 ease-in-out"
                        :class="slideLeft ? 'gap-6' : 'gap-1'"
                    >
                        <a
                            class="bg-accent opacity-70 rounded-lg p-3 hover:opacity-80"
                            href="http://"
                            target="_blank"
                            rel="noopener noreferrer"
                            ><svg
                                xmlns="http://www.w3.org/2000/svg"
                                width="24"
                                height="24"
                                viewBox="0 0 24 24"
                                fill="none"
                                stroke="currentColor"
                                stroke-width="2"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                class="lucide text-primary lucide-linkedin"
                            >
                                <path
                                    d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
                                />
                                <rect width="4" height="12" x="2" y="9" />
                                <circle cx="4" cy="4" r="2" /></svg
                        ></a>
                        <a
                            class="bg-accent opacity-70 rounded-lg p-3 hover:opacity-80"
                            href="http://"
                            target="_blank"
                            rel="noopener noreferrer"
                            ><svg
                                xmlns="http://www.w3.org/2000/svg"
                                width="24"
                                height="24"
                                viewBox="0 0 24 24"
                                fill="none"
                                stroke="currentColor"
                                stroke-width="2"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                class="lucide text-primary lucide-facebook"
                            >
                                <path
                                    d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"
                                /></svg
                        ></a>
                        <a
                            class="bg-accent opacity-70 rounded-lg p-3 hover:opacity-80"
                            href="http://"
                            target="_blank"
                            rel="noopener noreferrer"
                            ><svg
                                xmlns="http://www.w3.org/2000/svg"
                                width="24"
                                height="24"
                                viewBox="0 0 24 24"
                                fill="none"
                                stroke="currentColor"
                                stroke-width="2"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                class="lucide text-primary lucide-instagram"
                            >
                                <rect
                                    width="20"
                                    height="20"
                                    x="2"
                                    y="2"
                                    rx="5"
                                    ry="5"
                                />
                                <path
                                    d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"
                                />
                                <line
                                    x1="17.5"
                                    x2="17.51"
                                    y1="6.5"
                                    y2="6.5"
                                /></svg
                        ></a>
                        <a
                            class="bg-accent opacity-70 rounded-lg p-3 hover:opacity-80"
                            href="http://"
                            target="_blank"
                            rel="noopener noreferrer"
                            ><svg
                                xmlns="http://www.w3.org/2000/svg"
                                width="24"
                                height="24"
                                viewBox="0 0 24 24"
                                fill="none"
                                stroke="currentColor"
                                stroke-width="2"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                class="lucide text-primary lucide-dribbble"
                            >
                                <circle cx="12" cy="12" r="10" />
                                <path
                                    d="M19.13 5.09C15.22 9.14 10 10.44 2.25 10.94"
                                />
                                <path
                                    d="M21.75 12.84c-6.62-1.41-12.14 1-16.38 6.32"
                                />
                                <path
                                    d="M8.56 2.75c4.37 6 6 9.42 8 17.72"
                                /></svg
                        ></a>
                    </div>
                    <div class="relative px-8 mx-8 bottom-0">
                        <Link href="/Contact">
                            <Button class="absolute bottom-8 left-0 right-0">
                                Contact Us</Button
                            >
                        </Link>
                    </div>
                </div>
            </div>
        </transition>
    </main>
</template>
