<template>
    <div class="box">
        <div class="box1">
            <UserSideBar />
        </div>
        <div class="box2 p-4">
            <h1>User Page</h1>
            <UserTodo />
        </div>
    </div>
</template>
<script>
import UserSideBar from './UserSideBar.vue';
import UserTodo from './UserTodo.vue';

export default {
    name: 'User',
    components: {
        UserSideBar,
        UserTodo,
    },
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