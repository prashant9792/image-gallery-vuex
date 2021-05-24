<template>
    <div class="ui secondary pointing menu">
        <a class="item">
            Image
        </a>
        <div class="right menu">
            <div v-if="isLogedIn" class="horizontal">
                <router-link to="/" class="item">Gallery</router-link>
                <router-link to="/upload" class="item">Upload</router-link>
                <a class="item" @click="logout">logout</a>
            </div>
            <a v-else class="ui item active" href="#" @click="login">
                Login
            </a>
        </div>
    </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex';

export default {
    name: 'AppHeader',
    computed: mapGetters(['isLogedIn']),
    methods: mapActions(['login','logout'])
}
</script>
<style scoped>
.horizontal {
    display: flex;
    flex-direction: row;
}
.secondary {
    font-size: 20px;
}

.secondary a.router-link-exact-active {
    background-color: transparent;
    -webkit-box-shadow: none;
    box-shadow: none;
    border-color: #1b1c1d;
    font-weight: 700;
    color: rgba(0,0,0,.95);
}
</style>