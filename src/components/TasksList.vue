<template>
    <!-- 2. Создайте компонент "TaskList", который будет отображать список задач в
    массиве tasks. Каждая задача должна иметь свойства: id, title, description и
    completed. -->
    <div>
    <h1>Hello from component!</h1>
    <ul>
        <li v-for="task in tasks" :key="task.id">
            {{ task.id }}/ {{ task.title }} - {{ task.description }} ({{ task.completed ? 'Завершено' : 'Не завершено'}})
        </li>
    </ul>
    <p>Всего задач: {{ countTasks }}</p>
    </div>
</template>

<script>
export default {
    props: ['tasks'],
    // 3. В компоненте "TaskList" создайте computed свойство, которое будет отображать
    // общее количество задач в списке.
    computed: {
        countTasks() {
            return this.tasks.length;
        }
    }
}

</script>