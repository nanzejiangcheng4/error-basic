<template>
  <ul>
    <li>
      <NuxtLink v-bind:to="{ name: 'errorHandlerBasic' }">
        エラー表示実験
      </NuxtLink>
    </li>
    <li>
      <NuxtLink v-bind:to="{ name: 'errorHanlerNavigate' }">
        画面表示のエラー実験
      </NuxtLink>
    </li>
    <li>
      <NuxtLink v-bind:to="{ name: 'errorHandlerFatal' }">
        致命的エラー発生実験
      </NuxtLink>
    </li>
    <li>
      <NuxtLink v-bind:to="{ name: 'errorHandlerServer' }">
        <!-- todo: errorHandlerServerページの作成から -->
        サーバーエラー発生実験
      </NuxtLink>
    </li>
  </ul>
</template>
