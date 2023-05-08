<template>
    <div class="box">
        <div class="box1">
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
                <button class="btn btn-dark">Log Out</button>
            </div>
        </div>
        <div class="box2 p-4">
            <h1>User Page</h1>
            <UserTodo />
        </div>
    </div>
</template>
<script>
import Sidebar from './Sidebar.vue'
import UserTodo from './UserTodo.vue';

export default {
    name: 'User',
    components: {
        Sidebar,
        UserTodo,
    }
}
</script>

<style scoped>
.box {
    display: flex;
}

.box1 {
    flex-basis: 20%;
}

.box2 {
    flex-basis: 80%;
}
</style>