<template>
<div>
  <h1>{{ site_name }}</h1>
</div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import { computed } from 'vue'
import { useStore } from 'vuex'

@Options({
  props: {
    msg: String,
  },
})

export default class Contact extends Vue {
    site_name = "WorldAnchor";
}
</script>
