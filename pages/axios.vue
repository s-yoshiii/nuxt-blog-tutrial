<template>
  <div>
    <p>{{ ip }}</p>
    <button @click="getIp">IPアドレスを取得</button>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      ip: "0.0.0.0",
    };
  },
  methods: {
    async getIp() {
      this.ip = await this.$axios.$get("http://icanhazip.com");
    },
  },
};
</script>
