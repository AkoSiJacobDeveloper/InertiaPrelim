<script setup>
import { Link } from '@inertiajs/vue3';
import { ref } from 'vue'
import MainLayout from './MainLayout.vue';

const message = ref("This is an Inertia App.")

</script>

<template>
    <MainLayout>
        <div class="d-flex justify-content-center align-items-center flex-column welcome-container">
            <h1 class="text-9xl uppercase">Hello World</h1>
            <div>{{ message }}</div>
            <!-- <Link class="underline text-blue-700" href="/categories">Go to /categories</Link> <br>
            <Link class="underline text-blue-700" href="/products">Go to /products</Link> -->
        </div>
    </MainLayout>
</template>

<style scoped>
.welcome-container {
    height: 90vh;
}
</style>
