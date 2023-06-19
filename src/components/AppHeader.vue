<script>
    export default {
        name: 'AppHeader',
        data() {
            return {
                
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <header>
        <nav class="navbar bg-light">
            <div class="container-fluid">
                <a class="navbar-brand fw-bold" href="#">
                <img src="../assets/img/logo.png" alt="Logo" class="d-inline-block align-text-top">
                Yu-Gi-Oh Api
                </a>
            </div>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixing.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    img{
        width: 100px;
        object-fit: cover;
        height: 30px;
    }
</style>
