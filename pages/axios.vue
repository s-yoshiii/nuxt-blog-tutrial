<template>
  <div>
    <p>{{ ip }}</p>
    <button>IPアドレスを取得</button>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      ip: "0.0.0.0",
    };
  },
};
</script>
