<template>
    <!-- 4. Создайте компонент "Task", который будет представлять отдельную задачу в
    списке. Компонент должен отображать заголовок и описание задачи -->
    <!-- 6. Реализуйте функционал удаления задачи из списка. В компоненте "Task"
    добавьте кнопку "Удалить", которая при нажатии будет удалять
    соответствующую задачу из массива tasks. -->
    <!-- 7. Добавьте возможность отметки выполнения задачи. В компоненте "Task"
    добавьте чекбокс, который будет менять статус completed соответствующей
    задачи. -->
    <div :class="SetClass(index)" class = 'cardCommon'>
        <span class="cross" @click="delTask">✖</span>
        <h4>{{ title }}</h4>
        <p>{{ desc }}</p>
        <p>{{ iscompleted }}</p>
        <input type="checkbox" class="checkbox" v-model="ischeck" @change="SetStatus">Done!
        <!-- <p v-if="checkDone">READY!!!</p> -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            ischeck: false
        }
    },
    props: ['title', 'desc', 'index', 'iscompleted'],
    methods: {
        SetClass(index) {
            return {
                'taskcardYellow'    : this.index%2 === 0,
                'taskcardPink'      : this.index%2 === 1
            }
        },
        delTask() {
            this.$emit('del', this.index);
        },
        SetStatus() {
            this.$emit('sendStatus', this.ischeck, this.index);
        }
    }
}

</script>

<style scoped>

.cardCommon {
  display: block;
  margin-bottom: 10px;
  font-size: 20px;
  height: 200px;
  width: 300px;
  padding: 5px;
  border: 1px solid rgba(128, 128, 128, 0.514);
  border-radius: 1px;
  outline: none;
  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.6), 10px 10px 70px rgba(0, 0, 0, 0.6);
}

.taskcardYellow {
  background: rgba(255, 251, 14, 0.97);
  transform: rotate(3deg);
}

.taskcardPink {
  background: rgba(239, 155, 238, 0.97);
  transform: rotate(-2.5deg);
}

/* Стили для крестика */
.cross {
  position: absolute;
  top: 3px;
  right: 5px;
  cursor: pointer;

.checkbox {
  position: absolute;
  bottom: 3px;
  left: 5px;
  cursor: pointer;
}
}



</style>