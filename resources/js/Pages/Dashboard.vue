<script setup lang="ts">
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';

import 'vue3-carousel/dist/carousel.css';
import { Carousel, Navigation, Slide } from 'vue3-carousel';
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <Carousel :items-to-show="1" :wrap-around="true">
            <Slide v-for="slide in 6" :key="slide">
                <div class="carousel_item">
                    <img id="slider" :src="`/images/carousel/slide${slide}.jpg`" alt="">
                </div>
            </Slide>

            <template #addons>
                <Navigation/>
            </template>
        </Carousel>

        <div class="relative -mt-[250px]">
            <div class="relative z-10 flex m-4">
                <div class="w-full p-2 mx-2 text-center bg-white text-md">
                    You are on amazon.com You can also shop on Amazon UK for millions of products with fast local delivery.
                </div>
            </div>
            <div class="relative z-10 grid grid-cols-3 m-4">
                <div class="p-1.5 flex" v-for="cat in $page.props.categories" :key="cat">
                    <Link href="/" class="bg-white p-5">
                        <div class="flex text-2xl font-extrabold">{{ cat.name }}</div>
                        <div class="flex">
                            <img class="object-fill" :src="`/images/categories/${cat.id}.png`" alt="">
                        </div>
                        <div class="pt-3 -mb-2 font-bold text-teal-800 cursor-pointer hover:underline hover:text-red-400">
                            See More
                        </div>
                    </Link>
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
