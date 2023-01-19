<template>
  <div>
    <div>BLOGページルーティング確認</div>
    <p>
      {{ $route.params.category }}カテゴリー の、{{
        $route.params.page
      }}ページ目です。
    </p>
  </div>
</template>
