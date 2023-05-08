<template>
    <div class="box">
        <div class="box1">
            <UserSideBar />
        </div>
        <div class="box2 p-4">
            <h1>Add Todo</h1>
            <form class="mt-4" style="max-width: 500px;">
                <div class="mb-3">
                    <label for="exampleInputEmail1" class="form-label">To Do</label>
                    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp"
                        v-model="tasks.task">
                </div>
                <button type="button" class="btn btn-dark" @click="addTodo">Add Todo</button>
            </form>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import UserSideBar from './UserSideBar.vue';

export default
    {
        name: 'AddTodo',
        data() {
            return {
                tasks: {
                    task: ''
                }
            }
        },
        components: {
            UserSideBar
        },
        methods: {
            async addTodo() {
                // console.log("ok", this.tasks.task)
                const result = await axios.post("http://localhost:3000/tasks", {
                    task: this.tasks.task
                });

                if (result.status == 201) {
                    this.$router.push({ name: "User" });
                }
            }
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