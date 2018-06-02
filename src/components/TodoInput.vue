<template>
  <b-field>
    <b-input
      placeholder="TODOを入力"
      inline
      v-model="todo"
    >
    </b-input>

    <b-datepicker
      placeholder="期限を入力"
      v-model="limit"
    >
    </b-datepicker>

    <p class="control">
      <button class="button is-primary" @click="addTodo">登録</button>
    </p>
  </b-field>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

@Component
export default class TodoInbput extends Vue {
  @Prop({ type: Array })
  private todoList!: object[];

  private todo!: string;
  private limit!: Date;

  addTodo(): void {
    if (!this.todo || !this.limit) {
      this.$dialog.alert("TODOと日付を入力してください");
      return;
    }
    const todoData = {
      todo: this.todo,
      limit: this.limit.toLocaleDateString()
    };

    this.todoList.push(todoData);
  }
}
</script>

<style scoped>
</style>
