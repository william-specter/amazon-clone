<script setup lang="ts">
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';

import 'vue3-carousel/dist/carousel.css';
import { Carousel, Navigation, Slide } from 'vue3-carousel';
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <Carousel :items-to-show="1" :wrap-around="true">
            <Slide v-for="slide in 10" :key="slide">
                <div class="carousel_item">
                    <img src="https://via.placeholder.com/3000x1200.png/004466?text=Testing" alt="">
                </div>
            </Slide>

            <template #addons>
                <Navigation/>
            </template>
        </Carousel>

        <div class="relative -mt-[300px]">
            <div class="relative z-10 flex m-4">
                <div class="w-full p-2 mx-2 text-center bg-white text-md">
                    You are on amazon.com You can also shop on Amazon UK for millions of products with fast local delivery.
                </div>
            </div>
            <div class="relative z-10 grid grid-cols-3 m-4">
                <div class="p-1.5 flex">
                    <div class="p-5 bg-white">
                        <div class="flex text-2xl font-extrabold">Computers</div>
                        <div class="flex">
                            <img src="https://via.placeholder.com/1097x756" alt="">
                        </div>
                        <div class="pt-3 -mb-2 font-bold text-teal-800 cursor-pointer hover:underline hover:text-red-400">
                            See More
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<style>
.carousel_item {
    font-size: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.carousel_prev,
.carousel_next {
    width: 40px;
    height: 200px;
    color: rgb(196, 196, 196);
    margin-top: -100px;
    border: transparent;
}

.carousel_prev:hover,
.carousel_next:hover {
    width: 40px;
    height: 200px;
    color: rgb(212, 212, 212);
    margin-top: -100px;
    border: 3px solid rgb(217, 217, 217);
}
</style>
