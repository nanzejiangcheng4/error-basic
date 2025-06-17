<script setup lang="ts">
import { ref } from "vue";

const boundaryKey = ref(0);

const onResetButtonClick = () => {
  boundaryKey.value++;
};
</script>

<template>
  <NuxtErrorBoundary :key="boundaryKey">
    <ErrorGeneratorBasic />
    <template v-slot:error="errorProps">
      <p>エラーが発生しました!</p>
      <p>{{ errorProps.error }}</p>
      <button v-on:click="onResetButtonClick">エラーを解消</button>
    </template>
  </NuxtErrorBoundary>
  <p>
    <NuxtLink v-bind:to="{ name: 'index' }"> 戻る </NuxtLink>
  </p>
</template>
