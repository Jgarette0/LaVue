<script setup>
import { Card } from "@/Components/ui/card";
import { CardHeader } from "@/Components/ui/card";
import { CardTitle } from "@/Components/ui/card";
import { CardContent } from "@/Components/ui/card";
import { CardFooter } from "@/Components/ui/card";
import { Button } from "@/Components/ui/button";
import { Link } from "@inertiajs/vue3";
</script>
<template>
    <div
        class="flex flex-col w-screen px-2 md:py-0 py-12 md:px-20 place-items-center justify-center md:h-[35rem]"
    >
        <Card
            class="md:w-5/6 w-screen md:h-[25rem] bg-secondary-foreground opacity-90 rounded-xl md:rounded-[4rem] flex flex-col place-items-center justify-center"
        >
            <CardHeader class="">
                <CardTitle
                    class="text-accent text-xl scale-110 md:scale-100 md:text-4xl"
                    >Ready to have a conversation?
                </CardTitle>
            </CardHeader>
            <CardContent
                class="text-accent text-lg md:text-xl text-justify md:text-center px-6 md:px-20"
            >
                We’re here to discuss how we can partner, sharing our knowledge
                and experience for your product development needs. Get started
                driving your business forward.
            </CardContent>
            <CardFooter class="text-accent">
                <Link href="/Contact">
                    <Button
                        class="md:text-2xl text-md px-6 py-6 md:py-8 md:px-8"
                        variant="secondary"
                        ><svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="32"
                            height="32"
                            viewBox="0 0 24 24"
                            fill="none"
                            stroke="currentColor"
                            stroke-width="2"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            class="lucide md:scale-100 scale-75 lucide-calendar-plus mr-4 text-[#2563eb]"
                        >
                            <path d="M8 2v4" />
                            <path d="M16 2v4" />
                            <path
                                d="M21 13V6a2 2 0 0 0-2-2H5a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h8"
                            />
                            <path d="M3 10h18" />
                            <path d="M16 19h6" />
                            <path d="M19 16v6" /></svg
                        >Schedule free consultation</Button
                    ></Link
                >
            </CardFooter>
        </Card>
    </div>
</template>
