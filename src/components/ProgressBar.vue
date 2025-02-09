<script setup lang="ts">
const props = defineProps<{
  percent: string
  percent2: string
  percent3: string
  percent4: string
  percent5: string
}>()

</script>

<template>
  <section id="🔥ProgressBar">
    <div id="🔥ProgressBar__Color"></div>
    <div id="🔥ProgressBar__Color"></div>
    <div id="🔥ProgressBar__Color"></div>
    <div id="🔥ProgressBar__Color"></div>
    <div id="🔥ProgressBar__Color"></div>
  </section>
</template>

<style lang="scss">
#🔥ProgressBar {
  position: relative;
  mask-image: url('../assets/progressbar.png');
  mask-repeat: no-repeat;
  width: 880px;
  height: 12px;
}

#🔥ProgressBar__Color {
  position: absolute;
  width: 2000px;
  height: inherit;

  &::after {
    content: '';
    position: absolute;
    left: 100%;
    width: 2px;
    height: inherit;
    background-color: #000;
  }
}

#🔥ProgressBar__Color:nth-of-type(1) {
  z-index: 5;
  width: calc(v-bind('props.percent') / 100 * 100%);
  background: #237CAB;
}

#🔥ProgressBar__Color:nth-of-type(2) {
  z-index: 4;
  width: calc(v-bind('props.percent2') / 100 * 100%);
  background: #5BB7E7;
}

#🔥ProgressBar__Color:nth-of-type(3) {
  z-index: 3;
  width: calc(v-bind('props.percent3') / 100 * 100%);
  background: #46D688;
}

#🔥ProgressBar__Color:nth-of-type(4) {
  z-index: 2;
  width: calc(v-bind('props.percent4') / 100 * 100%);
  background: #2F9B34;
}

#🔥ProgressBar__Color:nth-of-type(5) {
  z-index: 1;
  width: calc(v-bind('props.percent5') / 100 * 100%);
  background: #38640C;
}
</style>