<template>
    <div class="d-flex justify-content-center">
        <div class="card mt-3 w-100">
            <div class="card-body">
                <h4>To Do List</h4>
                <ul class="list-group mt-3">
                    <li class="list-group-item d-flex align-items-center justify-content-between" v-for="list in tasks"
                        :key="list.id">
                        <div class="d-flex gap-3">
                            <span class="message">{{ list.id }}</span>
                            <span class="message">{{ list.task }}</span>
                        </div>
                        <div class="btn-group d-flex gap-3">
                            <router-link :to="'/edittodo/' + list.id"><button
                                    class="btn btn-dark">Edit</button></router-link>
                            <button class="btn btn-dark" @click="remove(list.id)">Delete</button>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
  
<script>
import axios from 'axios'

export default {
    name: 'UserTodo',
    data() {
        return {
            tasks: {
                task: ''
            },
        }
    },
    methods: {
        display: async function () {
            let results = await axios.get("http://localhost:3000/tasks")
            // console.log(results);
            this.tasks = results.data;
        },
        remove: async function (id) {
            let results = await axios.delete("http://localhost:3000/tasks/" + id);

            if (results.status == 200) {
                this.display();
            }
        },
    },
    mounted() {
        this.display();
    }
}

</script>