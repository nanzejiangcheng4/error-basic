<script setup lang="ts">
import { ref } from "vue";
const boundaryKey = ref(0);
const onResetButtonClick = async (): Promise<void> => {
  await navigateTo("/");
  boundaryKey.value++;
};
</script>

<template>
  <NuxtErrorBoundary :key="boundaryKey">
    <ErrorGeneratorImmediate />
    <template #error="{ error }">
      <p>エラーが発生しました！</p>
      <p>{{ error }}</p>
      <button v-on:click="onResetButtonClick">エラーを解消</button>
    </template>
  </NuxtErrorBoundary>
  <p>
    <NuxtLink v-bind:to="{ name: 'index' }">戻る</NuxtLink>
  </p>
</template>
