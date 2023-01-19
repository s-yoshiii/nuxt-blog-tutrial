<template>
  <div>
    <div>BLOG詳細ページルーティング確認</div>
    <p>{{ $route.params.id }} エントリーです。</p>
  </div>
</template>
<script>
export default {
  validate({ params }) {
    return /^\d+$/.test(params.id);
  },
};
</script>
