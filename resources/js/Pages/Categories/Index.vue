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
            <div class="w-full  p-2 d-flex justify-content-between">
                <h1 class="text-black fs-2 m-0 fw-bold d-flex justify-content-center align-items-center">Categories Page</h1>
                <Link href="/products" class="productlist-btn border rounded d-flex justify-content-center align-items-center p-4 fw-bold">
                    Product List
                </Link>
            </div>

            <div class="container">
                <table class="w-100">
                    <thead class="">
                        <tr class="">
                            <th class="p-4 rounded-start text-left font-semibold uppercase text-white">Category</th>
                            <th class="p-4 rounded-end text-left font-semibold uppercase text-white">Description</th>
                        </tr>
                    </thead>

                    <tbody class="">
                        <tr v-for="category in categories" :key="category.id"
                            class="table-row pt-4">
                            <td class="py-4 px-6 rounded-start">{{ category.name }}</td>
                            <td class="py-4 px-6 rounded-end">{{ category.description }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </MainLayout>


</template>

<style scoped>


thead {
    background-color: #a31621;
}

.categories-container {
    background-color: #fcf7f8;;
}

.productlist-btn {
    transition: background-color 0.5s;
}

.productlist-btn:hover {
    background-color: #a31621;
    color: #fff;
}

.table-row:hover {
    background-color: #a31621;
    color: #fff;
}

table {
    border-collapse: separate;
    border-spacing: 0px 10px;
}
</style>
