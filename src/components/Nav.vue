<template>
    <nav class="navbar navbar-expand-md navbar-dark bg-dark mb-4">
        <div class="container-fluid">
            <RouterLink to="/" class="navbar-brand">Home</RouterLink>
            <div>
                <ul class="navbar-nav me-auto mb-2 mb-md-0">
                    <li class="nav-item">
                        <RouterLink to="/login" class="nav-link active">Login</RouterLink>
                    </li>
                    <li class="nav-item">
                        <RouterLink to="/register" class="nav-link active">Register</RouterLink>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script setup lang="ts">

</script>