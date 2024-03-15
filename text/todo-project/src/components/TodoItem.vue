<template>
  <div>
    <!-- todo表示エリア -->
    <el-col :span="12">
      <el-card  v-if="todo" class="box-card" shadow="hover" style="margin: 5px 0;">
        <el-row :gutter="12">
          <el-col :span="21">{{ todo }}</el-col>
          <el-col :span="3">
            <el-button @click="removeTodo" type="success" icon="el-icon-check" circle></el-button>
          </el-col>
        </el-row>
      </el-card>
      <!-- issue表示エリア -->
      <el-card v-if="issue" class="box-card" shadow="hover" style="margin: 5px 0;">
        <el-row :gutter="12">
          <el-col :span="21">{{ issue.title }}</el-col>
          <el-col :span="3">
            <el-button @click="closeIssue" type="success" icon="el-icon-check" circle></el-button>
          </el-col>
        </el-row>
      </el-card>
    </el-col>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    index: Number,
    todo: String,
    issue: Object,
  },
  methods: {
    removeTodo() {
      this.$emit('removeTodo', this.index);
    },
    closeIssue() {
      this.$emit('closeIssue', this.index);
    },
  }
}
</script>