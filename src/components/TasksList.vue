<template>
    <!-- 2. Создайте компонент "TaskList", который будет отображать список задач в
    массиве tasks. Каждая задача должна иметь свойства: id, title, description и
    completed. -->
    <div>
    <!-- <h1>Hello from component TaskList!</h1> -->
    <p>Total tasks: {{ countTasks }}</p>
    <p>Completed tasks: {{ countTasksDone }}</p>
    <div class="container_tasks">
    <TaskCard v-for="(task, index) in tasks" :key="task.id" :title="task.title" :desc="task.description" :index="index" :iscompleted="task.completed" @del="delTask" @sendStatus="SetStatus">
        
        <p><b>Task details:</b></p>
        <p>{{ task.description }}</p>

    </TaskCard>
    </div>

    </div>
</template>

<script>
import TaskCard from './TaskCard.vue';

export default {
    props: ['tasks'],
    // 3. В компоненте "TaskList" создайте computed свойство, которое будет отображать
    // общее количество задач в списке.
    computed: {
        countTasks() {
            return this.tasks.length;
        },
        countTasksDone() {
            return this.tasks.filter(item => item.completed === true).length;
        }
    },
    components: {
    TaskCard
    },
    methods: {
        delTask(id) {
            this.$emit('del', id)
        },
        SetStatus(ischeck, index) {
            this.$emit('sendStatus', ischeck, index);
        }
    }
}

</script>

<style scoped>
.container_tasks {
    display: flex;
    justify-content:space-around;
    flex-direction: row;
    flex-wrap: wrap;
}

p {
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    font-size: 1.3rem;
    font-weight: bold;
    color:  rgb(255, 255, 255);
    margin: 0;
    padding-left: 40px;
    padding-top: 10px;
    padding-bottom: 5px;
}

</style>