<script setup>
defineProps({
    product: {
        type: Object
    }
})

const image = 'images/dionega.jpeg'
</script>

<template>
    <div class="products-card rounded">
        <div class="container inner-container">
            <div class="image-container mb-2">
                <img class="rounded" :src="image" alt="Product Image">
            </div>
            <div class="d-flex text-container">
                <div class="d-flex justify-content-center flex-column">
                    <h1 class="fw-bold">Product Name: {{ product.name }}</h1>
                    <p class="fw-bold">Wholesale Price: ₱{{ product.whole_sale_price }}</p>
                    <p class="fw-bold">Retail price: ₱{{ product.retail_price }}</p>
                    <button class="buy-btn text-white p-1 rounded mt-2 w-50">Buy</button>
                </div>
            </div>
        </div>

    </div>
</template>

<style>
.products-card {
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}

.inner-container {
    padding: 12px;
}

.image-container {
    width: 100%;
}

img {
    width: 100%;
    height: 20vh;
    object-fit: cover;
}

.buy-btn {
   background-color: #a31621;
   transition: background-color 0.3s ease;
}

.buy-btn:hover {
    background-color: #d13a38;
}

</style>
