<template>
  <div id="app">
    <todo-header>
      TODO List
    </todo-header>

    <section class="container section">
      <todo-input :todoList.sync="todoList" />

      <todo-table :todoList.sync="todoList" />
    </section>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import TodoHeader from "@/components/TodoHeader.vue";
import TodoInput from "@/components/TodoInput.vue";
import TodoTable from "@/components/TodoTable.vue";

@Component({
  components: {
    TodoHeader,
    TodoInput,
    TodoTable
  }
})
export default class App extends Vue {
  protected todoList: object[] = [
    {
      todo: "Sample TODO",
      limit: new Date().toLocaleDateString()
    }
  ];
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
