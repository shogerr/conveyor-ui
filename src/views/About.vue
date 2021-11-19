<template>
  <div class="about">
    <banner :message="site_name" />
    <splash msg="Splash Message" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Splash from "@/views/Splash.vue"; // @ is an alias to /src
import Banner from "@/components/Banner.vue";

@Options({
  components: {
    Splash,
    Banner,
  },
})
export default class About extends Vue {
  site_name = window.location.origin;
}
</script>
