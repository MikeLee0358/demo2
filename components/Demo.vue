<script setup lang="ts">
import { ref, computed } from 'vue';

const theme = ref({
    color: 'red',
})
const props = defineProps<{
  color: string
  percent: string
  color2: string
  percent2: string
}>()


const border = computed(() => props.percent === '100%' ? '6px 0 0 6px;': '6px;')
console.log(border.value)
</script>

<template>
  <section id="Demo">
    <div id="Demo__Type"></div>
    <div id="Demo__Type2"></div>
  </section>
</template>

<style lang="scss">
#Demo {
  position: relative;
  width: 880px;
  height: 12px;

}

#Demo__Type {
  border-radius: v-bind('border');
  position: absolute;
  height: inherit;
  z-index: 1;
  width: v-bind('props.percent');
  background: v-bind('props.color');

  // &::after {
  //   content: '';
  //   position: absolute;
  //   left: 100%;
  //   width: 2px;
  //   height: inherit;
  //   background-color: #000;
  // }
}

#Demo__Type2 {
  border-radius: 6px;
  position: absolute;
  height: inherit;
  width: v-bind('props.percent2');
  background: v-bind('props.color2');

}
</style>