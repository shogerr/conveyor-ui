<template>
  <emoji>
    <h1>{{ message }}</h1>
  </emoji>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Emoji from "@/components/Banners/Emoji.vue";

@Options({
  components: {
    Emoji,
  },
  props: {
    message: String,
  },
})
export default class Banner extends Vue {
  subtitle = "Second Message";

  message!: string;

  get splitMessage(): Array<unknown> {
    return this.message.split("");
  }

  randomInt(max: number): number {
    return Math.floor(Math.random() * max);
  }

  splitString(str: string): Array<unknown> {
    return str.split("");
  }

  mounted(): void {
    console.log("mounted");
  }
}
</script>

<style scoped lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Ewert&display=swap");
h1 {
  font-size: 10em;
  //font-family: 'Ewert';
}
</style>
