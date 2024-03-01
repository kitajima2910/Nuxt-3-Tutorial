<template>
    <div>
        <Head>
            <Title>PXH2910 | {{ product.title }}</Title>
            <Meta name="description" :content="product.description" />
        </Head>

        <ProductDetails :product="product" />
    </div>
</template>

<script setup>
    const { id } = useRoute().params
    const uri = `https://fakestoreapi.com/products/${id}`

    const { data: product } = await useFetch(uri)

    if (!product.value) {
        throw createError({
            statusCode: 404,
            statusMessage: 'Product not found',
            fatal: true
        })
    }

    // Nếu sử dụng 'product' ở đây thì sẽ bị undefined vì await chưa có
    // useHead({
    //     title: `PXH2910 | ${product.title}`,
    //     meta: [
    //         {
    //             name: 'description',
    //             content: `${product.description}`
    //         }
    //     ]
    // })

    definePageMeta({
        layout: 'products'
    })
</script>

<style scoped>

</style>