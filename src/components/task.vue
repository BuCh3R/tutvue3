<script setup>
import { ref } from 'vue';
const tasks = ref([]);
const newTask = ref('');

const addTaskToList = () => {
    console.log(newTask.value);
    tasks.value.push(newTask.value);
    newTask.value = "";
}
</script>

<template>
    <form @submit.prevent="addTaskToList">
        <input type="text" v-model="newTask">
        <button>Tilføj opgave</button>
    </form>
    <br>
    <ul>
        <li v-for="(task, index) in tasks" :key="index">
            {{ task }}
        </li>
    </ul>
</template>