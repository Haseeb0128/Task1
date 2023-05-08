<template>
    <div class="d-flex flex-column flex-shrink-0 p-3 bg-light" style="height: 100vh;">
        <a href="/" class="d-flex align-items-center mb-3 mb-md-0 me-md-auto link-dark text-decoration-none">
            <span class="fs-4">Welcome</span>
        </a>
        <hr>
        <ul class="nav nav-pills flex-column mb-auto">
            <li class="nav-item">
                <a href="#" class="nav-link link-dark">
                    <router-link to="/user" style="text-decoration: none; color: black;">View Todo</router-link>
                </a>
            </li>
            <li class="nav-item">
                <a href="#" class="nav-link link-dark">
                    <router-link to="/addtodo" style="text-decoration: none; color: black;">Add Todo</router-link>
                </a>
            </li>
        </ul>
        <hr>
        <button class="btn btn-dark" v-on:click="logout">Log Out</button>
    </div>
</template>

<script>
export default {
    name: 'UserSideBar',
    methods: {
        logout() {
            localStorage.clear();
            this.$router.push({ name: 'Login' })
        }
    }
}
</script>

<style></style>