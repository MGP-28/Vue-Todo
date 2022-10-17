<template>
    <div>
        <TaskCounter :tasksDone="getCompleted" :totalTasks="tasks.length" />
    </div>
    <div class="tasks-container border p-2">
        <TaskCard v-for="(task, idx) in tasks" :task="task" :key="idx"/>
    </div>
</template>

<script>
import { mapState } from 'pinia'
import { tasksStore } from '../stores/Tasks'
import TaskCard from '../components/TaskCard.vue';
import TaskCounter from '../components/taskCounter.vue';
    export default {
    name: "TasksView",
    computed:{
        ...mapState(tasksStore, ['tasks', 'getCompleted']),
    },
    components: { TaskCard, TaskCounter }
}
</script>

<style scoped>
.tasks-container{
    display: flex;
    flex-direction: column;
}
</style>