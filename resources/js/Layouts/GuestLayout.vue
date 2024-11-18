<script setup lang="ts">
import ApplicationLogo from '@/Components/ApplicationLogo.vue';
import { Link } from '@inertiajs/vue3';
</script>

<template>
    <div
        class="flex flex-col items-center min-h-screen pt-6"
    >
        <div>
            <Link href="/">
                <img class="h-12 fill-current text-gray-500" src="/images/logo/AMAZON_LOGO_DARK.png" alt="">
            </Link>
        </div>

        <div
            class="w-full px-6 py-4 mt-6 overflow-hidden bg-white border border-gray-300 max-w-[400px] rounded-sm">
            <slot />
        </div>
        <div v-if="$page.url === '/login'" class="w-[400px]">
            <div class="text-center text-sm text-gray-600 font-bold py-4">New to Amazon?</div>
            <div class="w-full border border-gray-500 bg-gray-200 text-sm font-extrabold rounded-md p-2 hover:border-gray-300 text-center">
                <Link :href="route('register')">
                    Create your Amazon account
                </Link>
            </div>
        </div>
    </div>
</template>
