<template>
    <div>
        
    </div>
</template>

<script>
export default {
    props: ['tasks'],
    computed: {
        countTasks() {
            return this.tasks.length;
        }
    }
}

</script>