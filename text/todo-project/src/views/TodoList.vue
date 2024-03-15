<template>
  <div>
    <h1>Todoリスト</h1>
    <form @submit.prevent="addTodo()">
      <el-input v-model="todo"></el-input>
    </form>
    <el-row :gutter="20">
      <el-col :span="12" v-for="( todo, index ) in todos" :key="index">
        <el-card shadow="hover" class="box-card">
          {{ todo }}
          <el-button type="success" icon="el-icon-check" circle @click="removeTodo(index)"></el-button>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  data() {
    return {
      todo: '',
      todos: []
    }
  },
  methods: {
    addTodo() {
      this.todos.push(this.todo);
      this.todo = '';
    },
    removeTodo(index) {
      this.todos.splice(index, 1); //--1
    }
  }
}
</script>