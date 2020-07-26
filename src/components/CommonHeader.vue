<template>
  <header>
    <div class="l-content">
      <el-button plain icon="el-icon-menu" size="mini" @click="collapseMenu"></el-button>
      <el-breadcrumb separator="/">
        <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
        <el-breadcrumb-item :to="current.path" v-if="current">
          {{ current.label }}
        </el-breadcrumb-item>
      </el-breadcrumb>
    </div>
    <div class="r-content">
      <el-dropdown trigger="click">
        <span class="el-dropdown-link"><img :src="useImg" class="user"/></span>
        <el-dropdown-menu slot="dropdown" size="smallmini">
          <el-dropdown-item>个人中心</el-dropdown-item>
          <el-dropdown-item>退出</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </header>
</template>

<script>
import { mapState } from 'vuex'
export default {
  computed: {
    ...mapState({
      current: state => state.tab.currentMenu
    })
  },
  data() {
    return {
      useImg: require('../assets/images/头像.png')
    }
  },
  methods: {
    collapseMenu() {
      this.$store.commit('collapseMenu')
    }
  }
}
</script>

<style lang="scss" scoped>
header {
  display: flex;
  height: 100%;
  align-items: center;
  justify-content: space-between;
}
.l-content {
  display: flex;
  align-items: center;
  .el-button {
    margin-right: 20px;
  }
}
.r-content {
  .user {
    width: 40px;
    height: 40px;
  }
}
</style>
<style lang="scss">
.el-breadcrumb__item {
  .el-breadcrumb__inner {
    color: #f4f4f4;
  }
  &:last-child {
    .el-breadcrumb__inner {
      color: #ffffff;
    }
  }
  .el-breadcrumb__inner {
    color: #666666;
    font-weight: normal;
  }
}
</style>
