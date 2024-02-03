<template>
  <div class="login">
    <img src="@/assets/images/login.jpg" alt="" />
    <div class="box">
      <div class="title">博客系统</div>
      <el-form ref="form" :model="form" label-width="0">
        <el-row :gutter="20" class="row-class">
          <el-col :span="4">用户名</el-col>
          <el-col :span="20" style="height: 100%">
            <el-form-item>
              <el-input
                style="width: 100%"
                v-model="form.username"
                size="mini"
              ></el-input> </el-form-item
          ></el-col>
        </el-row>
        <el-row :gutter="20" class="row-class">
          <el-col :span="4">密码</el-col>
          <el-col :span="20" style="height: 100%">
            <el-form-item>
              <el-input
                style="width: 100%"
                v-model="form.password"
                size="mini"
              ></el-input> </el-form-item
          ></el-col>
        </el-row>
      </el-form>
      <el-row class="row-class" style="justify-content: center">
        <el-button type="primary" size="mini" @click="login">登录</el-button>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  name: "login",
  data() {
    return {
      form: {
        username: "",
        password: "",
      },
    };
  },
  methods: {
    login() {
      this.$router.push("/home");
    },
  },
};
</script>

<style lang="scss" scoped>
.login {
  position: relative;
  width: 100%;
  height: 100%;
  background: rgb(54, 156, 187);
  overflow: hidden;
  img {
    width: 100%;
    height: 100%;
  }
  .box {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 400px;
    height: 500px;
    background: rgba($color: #fff, $alpha: 0.7);
    transform: translate(-50%, -50%);
    border-radius: 10px;
    padding: 20px;
    display: flex;
    justify-content: center;
    flex-direction: column;
    box-sizing: border-box;
    .title {
      width: 100%;
      height: 60px;
      display: flex;
      justify-content: center;
      font-size: 24px;
      font-weight: 600;
    }
    .row-class {
      width: 100%;
      height: 40px;
      display: flex;
      justify-content: flex-start;
      align-items: center;
      font-size: 12px;
      margin: 20px 0;
    }
  }
}
</style>