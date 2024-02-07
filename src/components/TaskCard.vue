<template>
    <!-- 4. Создайте компонент "Task", который будет представлять отдельную задачу в
    списке. Компонент должен отображать заголовок и описание задачи -->
    <div class="taskcard">
        {{ title }} - {{ desc }}
    </div>
</template>

<script>
export default {
    props: ['title', 'desc']
}

</script>

<style>

.taskcard {
  display: block;
  margin-bottom: 10px;
  font-size: 20px;
  height: 40px;
  padding: 5px;
  border: 1px solid rgba(128, 128, 128, 0.514);
  border-radius: 5px;
  outline: none;
  background: rgba(128, 128, 128, 0.384);
}

</style>