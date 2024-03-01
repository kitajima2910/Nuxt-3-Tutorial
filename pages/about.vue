<template>
    <div>
        <h2>About</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque, voluptas. Magni possimus ratione eum quo ipsa dolor harum fugit beatae?</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque, voluptas. Magni possimus ratione eum quo ipsa dolor harum fugit beatae?</p>
        <div>{{ data }}</div>
    </div>
</template>

<script setup>
    const { data } = await useFetch('/api/currency/VND', {
        method: 'post',
        body: {
            age: 30
        }
    })
</script>

<style scoped>
    h2 {
        margin-bottom: 20px;
        font-size: 36px;
    }
    
    p {
        margin: 20px 0;
    }
</style>