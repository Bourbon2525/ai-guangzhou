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
        浮动的标题
      </div>
    </div>

    <!-- 下半部分：Tab 组件 -->
    <el-tabs v-model:selectedTab="activeTab">
      <el-tab-pane label="Tab 1" name="1">
        <div>这里是 Tab 1 的内容</div>
      </el-tab-pane>
      <el-tab-pane label="Tab 2" name="2">
        <div>这里是 Tab 2 的内容</div>
      </el-tab-pane>
      <el-tab-pane label="Tab 3" name="3">
        <div>这里是 Tab 3 的内容</div>
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import { ref } from 'vue';
import { ElTabs, ElTabPane } from 'element-plus';

// Ensure to import Element Plus styles in your main.js or similar entry file:
// import 'element-plus/dist/index.css';

export default {
  components: {
    ElTabs,
    ElTabPane
  },
  setup() {
    const activeTab = ref('1');
    return { activeTab };
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  height: 100vh;
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
  height: 200px;
  object-fit: cover;
}

.overlay-text {
  position: absolute;
  bottom: 30px;
  left: 50%;
  color: white;
  font-size: 24px;
  background-color: rgba(0, 0, 0, 0.5);
  padding: 5px 10px;
  border-radius: 5px;
}

.el-tabs {
  flex: 1;
}
</style>
