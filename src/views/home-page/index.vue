<template>
  <div class="home-page">
    <div class="show-box">
      <div class="title">{{ user.name }} 的博客</div>
      <div class="signature">{{ user.signature }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "home-page",
  data() {
    return {
      user: {
        name: "Robert",
        signature: "坚信自我，你能作茧自缚，就能破茧成蝶",
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.home-page {
  width: 100%;
  height: 100%;
  .show-box {
    width: 100%;
    height: 900px;
    background: url(~@/assets/images/home.jpg);
    background-size: 100% 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    flex-wrap: nowrap;
    color: #fff;

    .title {
      font-size: 48px;
      font-weight: 600;
    }
    .signature {
      height: 60px;
      font-size: 24px;
      line-height: 60px;
    }
  }
}
</style>