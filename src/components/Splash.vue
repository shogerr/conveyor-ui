<template>
  <div>
    <h1>{{ site_name }}</h1>
    <h2>{{ msg }}</h2>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
//import {Canvas3D, Object3DFacade} from 'troika-3d'
//import { Text } from 'troika-3d-text'
//import { Canvas3D } from 'troika-3d'
//import { Text3DFacade } from 'troika-3d-text'

@Options({
  props: {
    msg: String,
  },
})
export default class Splash extends Vue {
  site_name = window.location.origin;
  //displayText = new Text()
  //displayText.add("Testing")
}
</script>
