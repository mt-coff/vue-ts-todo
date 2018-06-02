<template>
  <nav class="navbar has-shadow is-spaced">
    <div class="container">
      <div class="navbar-brand">
        <div class="navbar-item">
          <p class="title">
            <slot></slot>
          </p>
        </div>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class TodoHeader extends Vue {}
</script>

<style scoped>
</style>
