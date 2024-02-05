<template>
    <div>
        <h2>Список1 задач5:</h2>
        <p>{{ mytasks }}</p>
        <p>Count: {{ countTasks }}</p>
        <!-- <Tasks></Tasks> -->
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
                    title: '1',
                    description: '1',
                    completed: '1'
                },
                {
                    id: '2',
                    title: '2',
                    description: '2',
                    completed: '2'
                },
                {
                    id: '3',
                    title: '3',
                    description: '3',
                    completed: '3'
                }
            ]
        }
    },
    components: {
        Tasks
    },
    computed: {
        countTasks() {
            return this.mytasks.length;
        }
    }
}
</script>

<style>
</style>
