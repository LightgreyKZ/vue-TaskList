<template>
    <div>
        <h2>My task list</h2>
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
                    title: 'Meet Jane',
                    description: 'Train will arrive at 8 a.m.',
                    completed: false
                },
                {
                    id: 2,
                    title: 'Go to school',
                    description: 'Preparing for celebrate New Year.',
                    completed: false
                },
                {
                    id: 3,
                    title: 'Have lunch with Ben',
                    description: 'Do not forget take gift for him',
                    completed: false
                },
                {
                    id: 4,
                    title: 'Go cinema at 7 p.m.',
                    description: 'Try dont be late',
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
        if (title.length > 0 && desc.length > 0) {
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
        }
        else 
        return 0;
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
    font-family: "Roboto", sans-serif;
}

.board {
    background-image: url('../src/assets/images/paymo-JXyY3jRV9oI-unsplash.jpg');
    background-position:left;
    background-size: cover;
    background-repeat: no-repeat;
    min-height: 600px;
    margin-bottom: 1rem;
}

</style>
