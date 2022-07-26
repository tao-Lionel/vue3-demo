<template>
  <input ref="divRef" v-model="state1.count" type="text" />
  <button @click="handleClick">{{ demoComputed }}</button>

  <ul>
    <li v-for="item in list" ref="itemRefs" :key="item">
      {{ item }}
    </li>
  </ul>
</template>

<script lang="ts" setup>
import { reactive, ref, nextTick, shallowReactive, computed, watch, watchEffect, watchPostEffect, onMounted, Ref, toRefs } from "vue";

// export default {
//   setup() {
// 深层响应
const state1 = reactive({
  count: 0,
  arr: [1],
  f: "wang",
  l: "tao",
});

const demoComputed = computed(() => {
  return state1.arr.length > 0 ? "yes" : "no";
});

onMounted(() => {});

const list = ref([1, 2, 3, 4, 56]);
const itemRefs = ref([]);

function handleClick() {
  state1.count++;
}
defineExpose({
  list,
});

// return {
//   ...toRefs(state1),
//   demoComputed,
//   list,
//   itemRefs,
//   handleClick,
// };
//   },
// };
</script>

<style scoped></style>
<!-- <template>
</template>

<script lang="ts">

import { defineComponent } from "vue"

export default defineComponent({
  name: "",
  components: {},
  async setup() {

    return {
    }

  }
})
</script> -->
