<script setup>
import { Link } from '@inertiajs/vue3';
import MainLayout from '../MainLayout.vue';
import ProductCard from '../../Components/ProductCard.vue';

defineProps({
    products: {
        type: Array,
    },
    categories: {
        type: Array,
    },
    category:{
        type: Object,
    }
})

</script>

<template>
    <MainLayout>
        <div class="">
        <!-- Sidebar (Categories) -->
        <!-- <div class="w-1/4 bg-gray-900 p-6 shadow-lg rounded-r-lg">
            <Link href="/products" class="text-3xl font-bold text-gray-300 cursor-pointer">Categories</Link>
            <div class="space-y-4 mt-6">
                <Link v-for="category in categories" :key="category.id" :href="`/products/${category.id}`"
                    class="block py-3 px-5 text-sm text-white bg-gray-600 hover:bg-blue-700 rounded-lg transition-all transform hover:scale-105 border-b border-gray-700">
                {{ category.name }}
                </Link>
            </div>
        </div> -->

        <!-- Main Content (Products List) -->
        <div class="container overflow-scroll" style="scrollbar-width: none;">
            <div class="d-flex justify-content-between p-2">
                <h1 v-if="!category" class="text-black fs-2 m-0 fw-bold d-flex justify-content-center align-items-center">Products List</h1>

                <h1 class="text-3xl font-bold text-gray-100 mb-6" style="margin: 0 !important;" v-if="category">{{ category.name }}</h1>
                <Link href="/categories" class="category-btn border rounded d-flex justify-content-center align-items-center p-3 fw-bold">Category List</Link>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div v-for="product in products" :key="product.id">
                    <ProductCard :product="product"/>
                </div>

            </div>

        </div>
    </div>
    </MainLayout>

</template>

<style scoped>
.sidebar {
    background-color: #1f2937;
}

.sidebar .link {
    transition: background-color 0.3s ease, transform 0.2s ease;
}

.sidebar .link:hover {
    background-color: #2563eb;
    transform: scale(1.05);
}

table {
    border-collapse: collapse;
    width: 100%;
}

th,
td {
    padding: 16px;
    text-align: left;
    border-bottom: 1px solid #2d3748;
}

th {
    background-color: #2d3748;
}

tr:hover {
    background-color: #4a5568;
}

.category-btn {
    transition: background-color 0.5s;
}

.category-btn:hover {
    background-color: #a31621;
    color: #fff;
}
</style>
