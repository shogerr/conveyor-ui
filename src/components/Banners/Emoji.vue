<template>
  <div class="body-wrap clip-animation">
    <div class="text-wrap">
      <slot />
    </div>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Emoji extends Vue {}
</script>

<style scoped lang="scss">
$char-one: ⚓;
$char-two: 🛸;
.body-wrap {
  background: url("data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%22-5 -4 25 25%22>\
    <foreignObject width=%22100%25%22 height=%22100%25%22>" + $char-one + "</foreignObject></svg>"),
    url("data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%222.5 0 50 50%22>\
    <foreignObject width=%22100%25%22 height=%22100%25%22>" + $char-two + "</foreignObject></svg>"),
    transparent;
  background-size: 35px 35px;
  height: 100vh;
  line-height: 100vh;
  text-align: center;
  background-color: black;
  color: white;
}

.text-wrap {
  display: inline;
  color: rgb(255, 0, 0) !important;
  font-weight: 900;
  font-size: 5vw;
  background-color: white !important;
}
</style>
