<template>
<div>
  <h1>{{ site_name }}</h1>
  <h2>{{ msg }}</h2>
</div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    msg: String,
  },
})

export default class Splash extends Vue {
    site_name = window.location.origin;
}
</script>
