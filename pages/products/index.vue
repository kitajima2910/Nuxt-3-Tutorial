<template>
    <div>
        <div class="grid grid-cols-4 gap-5">
            <div v-for="p in products">
                <ProductCard :product="p" />
            </div>
        </div>
    </div>
</template>

<script setup>
    definePageMeta({
        layout: 'products'
    })

    // fetch the products
    const { data: products } = await useFetch('https://fakestoreapi.com/products')

    useHead({
        title: 'PXH2910 | Kitajima2910',
        meta: [
            {
                name: 'description',
                content: 'NuxtJS 3'
            }
        ]
    })
</script>

<style scoped>

</style>