<template>
    <div class="task-card-container border border-white rounded">
        <div class="border w-5 h-5 rounded-full task-card-status" :class="taskStatusCSSClass"></div>
        <span class="text-left">{{task.description}}</span>
        <button class="btn btn-primary border">Detalhe</button>
    </div>
</template>

<script>
    export default {
        name: "TaskCard",
        props:[
            'task'
        ],
        computed:{
            taskStatusCSSClass(){
                return this.task.isCompleted ? "bg-primary" : ""
            }
        }
    }
</script>

<style scoped>
.task-card-container{
    display: grid;
    align-items: center;
    grid-template-columns: auto 1fr auto;
    gap: 10px;
    padding: 20px 20px 20px 40px;
}
</style>