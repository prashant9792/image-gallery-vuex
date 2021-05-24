<template>
    <div>
        <div v-if="isLogedIn" class="image-container">
            <img v-for="image in allImages" :src="image.link" :key="image" />
        </div>
        <h2 v-else>Login in to start</h2>
    </div>
</template>

<script>
import {  mapActions, mapGetters } from 'vuex';
export default {
    name: 'ImageList',
    computed: mapGetters(['allImages', 'isLogedIn']),
    methods: mapActions(['fetchImages']),
    created() {
        this.fetchImages();
    }
    
}
</script>
<style scoped>
.image-container {
    column-count: 3;
    column-gap: 15px;
}
img {
    max-width: 100%;
    border: 2px solid #ccc;
}
</style>