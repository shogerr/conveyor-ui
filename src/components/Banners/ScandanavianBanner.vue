<template>
  <div id="body-wrap">
    <div class="wrap">
      <div class="block-title">
        <div class="title-1">
          <span v-for="m in splitString(message)" :key="m">
            {{ m }}
          </span>
        </div>
        <div class="title-2">
          <span v-for="m in splitString(subtitle)" :key="m">
            {{ m }}
          </span>
        </div>
      </div>
      <template v-for="n in 63" :key="n">
        <div class="block" :class="'style-' + randomInt(13)" />
      </template>
      <div class="block style-13" />
      <div class="block block-last" />
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    message: String,
  },
})
export default class Banner extends Vue {
  subtitle = "Second Message";
  message!: "Private Message";

  get splitMessage() {
    return this.message.split("");
  }

  randomInt(max: number) {
    return Math.floor(Math.random() * max);
  }

  splitString(str: string) {
    return str.split("");
  }
  created() {
    console.log(`${this.message}`);
  }
  onMounted() {
    console.log(`${this.message}`);
  }
}
</script>

<style scoped lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Ewert&display=swap");
h1 {
  font-size: 10em;
  //font-family: 'Ewert';
}

$gray-lighter: #f7f7f7;
$gray-light: #dbdbdd;
$gray-dark: #aeafb3;
$gray-darker: #454547;
$pink: #e89d93;
$yellow: #eec71a;

$block-length: 125px;
$col-num: 7;

#body-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  background: powderblue;
}
.wrap {
  background: $gray-lighter;
  margin-top: 50px;
  margin-bottom: 50px;
  width: $block-length * $col-num;
  border-radius: 5px;
  overflow: hidden;
  display: grid;
  grid-template-columns: repeat($col-num, 1fr);
}
.block-title {
  background: $gray-lighter;
  grid-column-start: 2;
  grid-column-end: -1;
  grid-row-start: $col-num - 1;
  grid-row-end: $col-num + 1;
  display: flex;
  padding: 3em 3.5em;
  transition: padding 0.3s linear;
  align-items: stretch;
  justify-content: space-between;
  flex-direction: column;
  > div {
    display: flex;
    justify-content: space-between;
  }
  &:hover {
    padding: 3em;
    .title-1 {
      order: 0;
    }
    .title-2 {
      order: 2;
    }
    .title-3 {
      order: 1;
    }
  }
}
.title-1,
.title-3 {
  font-weight: 800;
  font-size: 3em;
}
.title-2 {
  font-weight: 600;
  font-size: 1.1em;
}
.title-3 {
  order: 1;
}
.block {
  width: $block-length;
  height: $block-length;
}
.style-1 {
  background: $gray-darker;
}
.style-2 {
  //opting for classic css triangles technique here rather than backgrounds, just because
  width: 0;
  height: 0;
  border: $block-length/2 solid $gray-lighter;
  border-top-color: $gray-dark;
  border-bottom-color: $gray-dark;
  //to account for a pixel-rounding annoyance:
  background: $gray-dark;
  padding-top: 1px;
}
.style-3 {
  background-image: linear-gradient(135deg, $pink 50%, $gray-light 50%);
}
.style-4 {
  background-image: linear-gradient(
    $gray-lighter,
    $gray-lighter 7px,
    $gray-darker 7px,
    $gray-darker
  );
  background-size: 100% 14px;
}
.style-5 {
  background-image: linear-gradient(45deg, $yellow 50%, $gray-lighter 50%);
}
.style-6 {
  background-image: linear-gradient(135deg, $gray-darker 50%, transparent 50%),
    linear-gradient(
      $gray-lighter,
      $gray-lighter 7px,
      $gray-darker 7px,
      $gray-darker
    );
  background-size: 100%, 100% 14px;
}
.style-7 {
  background: linear-gradient(45deg, $gray-light 50%, transparent 50%),
    radial-gradient($gray-darker 4px, transparent 4px),
    radial-gradient($gray-darker 4px, transparent 4px), transparent;
  background-size: 100%, 24px 24px, 24px 24px, 100%;
  background-position: 0 0, -2px 6px, 10px 18px, 0 0;
}
.style-8 {
  background-image: linear-gradient(315deg, $yellow 50%, $gray-lighter 50%);
}
.style-9 {
  background-image: linear-gradient(225deg, $pink 50%, $gray-lighter 50%);
}
.style-10 {
  background: $gray-light;
}
.style-11 {
  background-image: linear-gradient(45deg, $pink 50%, $gray-lighter 50%);
}
.style-12 {
  background-image: linear-gradient(225deg, $yellow 50%, $gray-lighter 50%);
}
.style-13 {
  background: radial-gradient($gray-darker 3px, transparent 4px);
  background-size: $block-length/10 $block-length/10;
  background-position: 0 0;
}
.block-last {
  background-image: linear-gradient(
    to right,
    $pink,
    $pink 4px,
    $gray-lighter 4px,
    $gray-lighter
  );
  background-size: 8px 100%;
}
</style>
