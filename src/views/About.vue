<template>
  <div class="about">
    <splash msg='Splash Message'/>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Splash from "@/components/Splash.vue"; // @ is an alias to /src

@Options({
  components: {
    Splash,
  },
})
export default class About extends Vue {}
</script>
