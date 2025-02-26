<script setup>
import { Link } from '@inertiajs/vue3';
</script>

<template>
  <nav class="p-3">
        <div class="d-flex justify-content-between">
            <div class="text-white h2 fw-bold p-3 p-md-0">
                <h1 class="fw-bold m-0">Tocmo</h1>
            </div>
            <div class="d-flex gap-3 justify-content-center align-items-center">
                <Link href="/" class="text-white">Welcome</Link>
                <Link href="/home" class="text-white">Home</Link>
                <Link href="/about" class="text-white">About</Link>
                <Link href="/products" class="text-white">Products</Link>
                <Link href="/categories" class="text-white">Categories</Link>
            </div>
        </div>
  </nav>
<slot/>
</template>

<style>
</style>
