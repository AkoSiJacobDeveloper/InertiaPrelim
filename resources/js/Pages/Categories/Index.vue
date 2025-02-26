<script setup>
import { Link } from '@inertiajs/vue3';
import MainLayout from '../MainLayout.vue';
defineProps({
    categories: {
        type: Array,
    }
})
</script>

<template>
    <MainLayout>
        <div class="categories-container container" style="scrollbar-width: none;">
            <div class="w-full  p-6 flex justify-between items-center shadow-lg">
                <h1 class="text-2xl font-bold uppercase">Categories Page</h1>
                <Link href="/products" class="rounded-lg bg-gray-200 text-gray-900 font-semibold py-3 px-6 hover:bg-gray-600 hover:text-white transition duration-300 uppercase text-sm">
                    Product List
                </Link>
            </div>

            <div class="container">
                <table class="min-w-full table-auto">
                    <thead>
                        <tr class="">
                            <th class="py-3 px-6 text-left font-semibold uppercase">Category</th>
                            <th class="py-3 px-6 text-left font-semibold uppercase">Description</th>
                        </tr>
                    </thead>

                    <tbody class="divide-y divide-gray-600">
                        <tr v-for="category in categories" :key="category.id"
                            class="hover:bg-gray-700 transition duration-200">
                            <td class="py-4 px-6 text-gray-200">{{ category.name }}</td>
                            <td class="py-4 px-6 text-gray-400">{{ category.description }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </MainLayout>


</template>

<style scoped>
* {
    color: #000;
}

.categories-container {
    background-color: #fcf7f8;;
}
</style>
