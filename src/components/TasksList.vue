<template>
    <div>
    <h1>Hello!</h1>
    <p>{{ mytasks }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            mytasks: [
                {
                    id: '0',
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
    computed: {
        countTasks() {
            return this.mytasks.length;
        }
    }
}
</script>