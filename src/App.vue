<template>
    <div>
        <h2>Список задач:</h2>
        <Tasks :tasks="mytasks">
        </Tasks>
    </div>
</template>

<script>
import Tasks from '../src/components/TasksList.vue'

export default {
    data() {
        return {
            mytasks: [
                {
                    id: '1',
                    title: 'Task1',
                    description: 'Desc1',
                    completed: false
                },
                {
                    id: '2',
                    title: 'Task2',
                    description: 'Desc2',
                    completed: true
                },
                {
                    id: '3',
                    title: 'Task3',
                    description: 'Desc3',
                    completed: false
                }
            ]
        }
    },
    components: {
        Tasks
    }
}
</script>

<style>
</style>
