<template>
    <!-- 2. Создайте компонент "TaskList", который будет отображать список задач в
    массиве tasks. Каждая задача должна иметь свойства: id, title, description и
    completed. -->
    <div>
    <h1>Hello from component TaskList!</h1>
    <TaskCard v-for="task in tasks" :key="task.id" :title="task.title" :desc="task.description">

    </TaskCard>
    <p>Всего задач: {{ countTasks }}</p>
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
        }
    },
    components: {
    TaskCard
}
}

</script>