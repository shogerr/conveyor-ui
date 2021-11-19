<template>
  <component :is="bannerStyle" :message="message">
    {{ message }}
  </component>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Emoji from "@/components/Banners/Emoji.vue";
import Scandanavian from "@/components/Banners/Scandanavian.vue";
import RTVE from "@/components/Banners/RTVE.vue";

@Options({
  components: {
    Emoji,
    Scandanavian,
    RTVE,
  },
  props: {
    message: String,
  },
})
export default class Banner extends Vue {
  subtitle = "Second Message";
  message!: string;

  get bannerStyle(): string {
    console.log(this.$options);
    return "RTVE";
  }

  mounted(): void {
    console.log("Mounted a banner.");
  }
}
</script>
