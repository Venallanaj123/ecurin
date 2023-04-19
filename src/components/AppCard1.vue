<template>
    <div class="card">
        <img :src="imageSrc" alt="Card image">
        <div class="card-body">
            <h5 class="card-title">{{ title }}</h5>
            <p class="card-text">{{ text }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        imageSrc: {
            type: String,
            required: true,
        },
        title: {
            type: String,
            required: true,
        },
        text: {
            type: String,
            required: true,
        },
    },
};
</script>

<style>
.card {
    width: 18rem;
    margin: 1rem;
    border: 1px solid #ddd;
    border-radius: 5px;
    overflow: hidden;
}

.card img {
    height: 10rem;
    object-fit: cover;
}

.card-body {
    padding: 1rem;
}
</style>
