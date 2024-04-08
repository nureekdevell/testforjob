<template>
  <div class="">
    <div class="flex" @click="hideShow">
      <img class="w-5 h-5" src="../assets/right.png" v-if="!clickHideShow" />
      <img class="w-5 h-5" src="../assets/down.png" v-else />

      {{ label }}
    </div>
    <div v-if="clickHideShow" class="child">
      <tree-collapse
        v-for="item in nodes"
        :label="item.label"
        :nodes="item.nodes"
        :key="item.id"
      ></tree-collapse>
    </div>
  </div>
</template>

<script setup>
import { defineProps, ref } from "vue";

const clickHideShow = ref(false);

const hideShow = () => {
  clickHideShow.value = !clickHideShow.value;
};

const props = defineProps({
  label: String,
  nodes: Array,
});
</script>

<style scoped>
.child {
  margin-left: 10px;
}
</style>
