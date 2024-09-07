<template>
  <div class="container">
    <!-- 上半部分：图片 + 浮动标题 -->
    <div class="image-container">
      <img
          class="image"
          src="./assets/bg-title.jpg"
          alt="示例图片"
      />
      <div class="overlay-text">
        多福楼 御茶ノ水店
      </div>
    </div>

    <!-- 下半部分：Menu 组件 -->
    <div id="menu-container" class="menu-wrapper">
      <el-menu
          :default-active="activeMenu"
          class="custom-menu"
          mode="horizontal"
          @select="handleSelect"
      >
        <el-menu-item index="1">トップ</el-menu-item>
        <el-menu-item index="2">座席</el-menu-item>
        <el-sub-menu index="3">
          <template #title>メニュー・コース</template>
          <el-menu-item index="3-1">子菜单项 1</el-menu-item>
          <el-menu-item index="3-2">子菜单项 2</el-menu-item>
        </el-sub-menu>
        <el-sub-menu index="4">
          <template #title>写真</template>
          <el-menu-item index="4-1">子菜单项 1</el-menu-item>
          <el-menu-item index="4-2">子菜单项 2</el-menu-item>
        </el-sub-menu>
      </el-menu>

      <!-- 内容区域 -->
      <div class="content">
        <div v-if="activeMenu === '1'">
          <First/>
        </div>
        <div v-if="activeMenu === '2'">
          <!-- 第二页面的内容 -->
          <p>这是座席页面的内容。</p>
        </div>
        <div v-if="activeMenu === '3-1'">
          <!-- 子菜单 3-1 的内容 -->
          <p>这是子菜单项 1 的内容。</p>
        </div>
        <div v-if="activeMenu === '3-2'">
          <!-- 子菜单 3-2 的内容 -->
          <p>这是子菜单项 2 的内容。</p>
        </div>
        <div v-if="activeMenu === '4-1'">
          <!-- 子菜单 4-1 的内容 -->
          <p>这是子菜单项 1 的内容。</p>
        </div>
        <div v-if="activeMenu === '4-2'">
          <!-- 子菜单 4-2 的内容 -->
          <p>这是子菜单项 2 的内容。</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {ref} from 'vue';
import {ElMenu, ElMenuItem, ElSubMenu} from 'element-plus';
import First from "@/page/first.vue";

export default {
  components: {
    First,
    ElMenu,
    ElMenuItem,
    ElSubMenu,
  },
  setup() {
    const activeMenu = ref("1");

    const handleSelect = (index) => {
      activeMenu.value = index;
    };

    return {activeMenu, handleSelect};
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  padding: 0 15px;
}

.image-container {
  position: relative;
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.overlay-text {
  position: absolute;
  left: 50%;
  bottom: 50%;
  transform: translateX(-50%);
  color: black;
  font-size: 24px;
  padding: 5px 10px;
  border-radius: 5px;
  text-align: center;
}

.menu-wrapper {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center; /* 添加这一行 */
}

.custom-menu {
  --el-menu-active-color: #797152;
  --el-menu-hover-text-color: #797152;
  --el-menu-bg-color: #eeece4;
  --el-menu-hover-bg-color: #eeece4;


  width: 80%;
  display: flex;
  justify-content: space-evenly; /* 替代 space-between */
  position: sticky;
  top: 0px;
  z-index: 1000;
  background-color: white;
  margin-bottom: 10px;
}

.el-menu-item, .el-sub-menu {
  flex: 1; /* 每个菜单项占据相同的空间 */
  text-align: center; /* 居中对齐文本 */
  color: #797152; /* 设置文字颜色 */
  max-width: 200px;
}

.content {
  width: 70%;
  display: flex;
  justify-content: space-between;
}
</style>
