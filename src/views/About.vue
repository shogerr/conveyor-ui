<template>
  <div class="about">
    <banner message="Banner Message" />
    <splash msg="Splash Message" />
    <counter />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Splash from "@/components/Splash.vue"; // @ is an alias to /src
import Banner from "@/components/Banner.vue";
import Counter from "@/components/Counter.vue";

@Options({
  components: {
    Splash,
    Banner,
    Counter,
  },
})
export default class About extends Vue {}
</script>
