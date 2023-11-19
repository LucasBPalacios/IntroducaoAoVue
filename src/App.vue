<template>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <div class="container">
        <header class="d-flex justify-content-center py-3">
            <ul class="nav nav-pills">
                <li class="nav-item"><router-link to="/" class="nav-link active">Start</router-link></li>
                <li class="nav-item"><router-link to="Via-Cep" class="nav-link active">Via Cep</router-link></li>
                <li class="nav-item"><router-link to="About" class="nav-link active">About</router-link></li>
            </ul>
        </header>
        <router-view />
    </div>
</template>

<script setup>

</script>

<style scoped>
* {
    font-family: 'Segoe UI';
}

.nav-item {
 margin-right: 5px;
}
</style>
