<script setup lang="ts">
const onThrowErrorClick = async (): Promise<void> => {
  const asyncData = await useFetch("/api/generateError");
  const errorValue = asyncData.error.value;
  if (errorValue != null) {
    throw createError({
      message: `サーバーでエラーが発生しました: ${errorValue.message}`,
      statusCode: errorValue.statusCode,
      statusMessage: errorValue.statusMessage,
      fatal: true,
    });
  }
};
</script>

<template>
  <section>
    サーバーでエラーを<button v-on:click="onThrowErrorClick">発生</button>
  </section>
</template>
