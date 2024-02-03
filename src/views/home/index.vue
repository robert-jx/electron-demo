<template>
  <div class="home">
    <div class="top-bar">
      <div class="left">
        <div class="logo">MY BLOG</div>
        <div
          class="item"
          v-for="(item, index) in itemList"
          :key="index"
          @click="handleChange(item)"
        >
          {{ item.name }}
        </div>
      </div>
      <div class="right">
        <img src="@/assets/images/head.jpeg" alt="" />
      </div>
    </div>
    <div class="content">
      <component :is="activeName"></component>
    </div>
    <footer-box></footer-box>
  </div>
</template>

<script>
import homePage from "@/views/home-page";
import footerBox from "@/components/footer-box";
export default {
  name: "home",
  components: { homePage, footerBox },
  data() {
    return {
      itemList: [
        { name: "首页", component: "homePage" },
        { name: "博客", component: "blogPage" },
        { name: "相册", component: "photoPage" },
        { name: "朋友圈", component: "friendPage" },
        { name: "关于", component: "aboutPage" },
      ],
      activeName: "homePage",
    };
  },
  methods: {
    handleChange(item) {
      this.activeName = item.component;
    },
  },
};
</script>

<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
  overflow-y: auto;
  &::-webkit-scrollbar {
    display: none;
  }
  .top-bar {
    position: fixed;
    width: 100%;
    height: 60px;
    background: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-sizing: border-box;
    padding: 0 20px;
    .left {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      color: #494949;
      .logo {
        font-weight: 600;
        margin-right: 40px;
      }
      .item {
        margin: 0 10px;
        font-size: 12px;
        cursor: pointer;
      }
    }
    .right {
      display: flex;
      justify-content: flex-end;
      align-items: center;
      img {
        width: 40px;
        height: 40px;
        border-radius: 50%;
      }
    }
  }
  .content {
    width: 100%;
    min-height: calc(100% - 260px);
  }
}
</style>