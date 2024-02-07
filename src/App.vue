<template>
    <div>
        <h2>Список задач:</h2>
        <div class="board">
        <Tasks :tasks="mytasks" @del="delTask" @sendStatus="SetStatus">
        </Tasks>
        </div>
        <TaskForm @Add="AddTask">

        </TaskForm>
    </div>
</template>

<script>
import Tasks from '../src/components/TasksList.vue'
import TaskForm from '../src/components/TaskForm.vue'

export default {
    data() {
        return {
            lastid: 0,
            mytasks: [
                {
                    id: 1,
                    title: 'Task1111',
                    description: 'Desc1',
                    completed: false
                },
                {
                    id: 2,
                    title: 'Task2',
                    description: 'Desc2',
                    completed: true
                },
                {
                    id: 3,
                    title: 'Task3',
                    description: 'Desc3',
                    completed: false
                }
            ]
        }
    },
    components: {
    Tasks,
    TaskForm
    },
    methods: {
        AddTask(title, desc) {
        if (this.mytasks.length > 0) 
        {this.lastid = this.mytasks[this.mytasks.length-1].id}
        console.log(this.mytasks.length);
        console.log(this.lastid);
        this.mytasks.push({
          id: this.lastid + 1,
          title: title,
          description: desc,
          completed: false
          });
      },
      delTask(id) {
        // console.log(id);
        this.mytasks.splice(id,1);
      },
      SetStatus(ischeck, index) {
        const itemToUpdate = this.mytasks.find((item,i) => i == index);
        console.log(itemToUpdate);
        if (itemToUpdate) {
            itemToUpdate.completed = ischeck;
        }
        // console.log(ischeck);
        // console.log(index);
        console.log(itemToUpdate);
        }
    }
}
</script>

<style scoped>

* {
    box-sizing: border-box;
}

.board {
    background-image: url('../src/assets/images/empty-room-with-chairs-and-desks.jpg');
    background-position:left;
    background-size: cover;
    background-repeat: no-repeat;
}

</style>
