<template>
  <el-container class="home">
    <el-header>
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <el-menu-item style="margin-right: 200px;">
          <div style="font-size:12px;">
            <span>new精致的生活 ·</span>
            <span> Apple指南</span>
          </div>
        </el-menu-item>
        <el-menu-item index="1">苹果历代产品</el-menu-item>
        <el-menu-item index="2">Mac</el-menu-item>
        <el-menu-item index="3">iPhone</el-menu-item>
        <el-menu-item index="4">iPad</el-menu-item>
        <el-menu-item index="5">AirPods</el-menu-item>
        <el-menu-item index="6">Apple Watch</el-menu-item>
        <el-menu-item index="7">教育优惠</el-menu-item>
        <el-submenu index="8">
          <template slot="title">变得更强</template>
          <el-menu-item index="2-1">选项1</el-menu-item>
          <el-menu-item index="2-2">选项2</el-menu-item>
          <el-menu-item index="2-3">关于我</el-menu-item>
        </el-submenu>
        <el-menu-item index="9">
          <el-link href="https://itangqiao.top/index.php/33.html" target="_blank" :underline=false>留言板</el-link>
          <!-- <router-link to="www.baidu.com">留言板</router-link> -->
        </el-menu-item>
      </el-menu>
    </el-header>
    <el-container>
      <el-aside width="100px">
        <el-steps direction="vertical" :active="1">
          <el-step title="2020"></el-step>
          <el-step title="2021"></el-step>
          <el-step title="2022"></el-step>
        </el-steps>
      </el-aside>
      <el-main>
        <His-Product></His-Product>
      </el-main>
    </el-container>
    <el-footer>底部</el-footer>
  </el-container>
</template>

<script>
import Aside from '@/components/Aside.vue';
export default {
  name: 'IndexPage',
  data() {
    return {
      activeIndex: '1'
    }
  },
  beforeMount() {
    console.log(this);
    console.log('beforeMount');
  },
  mounted() {
    console.log('mounted');
  },
  methods: {
    handleSelect(a, b) {
      console.log(a, b);
    }
  },
  fetch() {
  },
  components: {
    Aside
  }
}
</script>
<style lang="less" scoped>
.home {
  height: 100%;

  .el-header,
  .el-footer {
    padding: 0;
    text-align: center;
    line-height: 60px;
  }

  .el-aside {
    display: flex;
    justify-content: center;
    padding: 20px 0;
  }

  .el-main {
    background-color: #E9EEF3;
    color: #333;
    // text-align: center;
    // line-height: 160px;
  }
}
</style>