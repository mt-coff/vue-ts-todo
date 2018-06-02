<template>
  <b-table
    :data="todoList"
  >
    <template slot-scope="props">
      <b-table-column field="todo" label="TODO">
        {{ props.row.todo }}
      </b-table-column>

      <b-table-column field="limit" label="期限">
        {{ props.row.limit }}
      </b-table-column>

      <b-table-column field="complete" label="">
        <button
         class="button is-success"
         @click="complete(props.index)"
        >
          完了
        </button>
      </b-table-column>
    </template>
  </b-table>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

@Component
export default class TodoTable extends Vue {
  @Prop({ type: Array })
  private todoList!: object[];

  complete(idx: number): void {
    const todoList = this.todoList.filter((e, i, a) => {
      return i !== idx;
    });

    this.$emit("update:todoList", todoList);
  }
}
</script>


<style scoped>
</style>
