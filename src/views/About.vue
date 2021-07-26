<template>
  <div class="about">
    <h1>{{ site_name }}</h1>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Contact from "@/components/Contact.vue"; // @ is an alias to /src

@Options({
  components: {
    Contact,
  },
})
export default class About extends Vue {
  site_name = "World-Anchor"
}
</script>
