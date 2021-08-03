<template>
  <div class="body-wrap">
    <slot />
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Emoji extends Vue {}
</script>

<style scoped lang="scss">
.body-wrap {
  background: url("data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 25 25%22>\
      <foreignObject width=%22100px%22 height=%22100px%22>‍⚓</foreignObject></svg>"),
    black;
  height: 100vh;
  position: absolute;
  background-size: 100px 100px;
}
</style>
