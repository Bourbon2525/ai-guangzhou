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

    <!-- 下半部分：Tab 组件 -->
    <div class="tabs-wrapper">
      <el-tabs v-model="activeTab" class="custom-tabs">
        <el-tab-pane label="トップ" name="tab1">
          <First/>
        </el-tab-pane>
        <el-tab-pane label="座席" name="tab2">
          <div>这里是 Tab 2 的内容</div>
        </el-tab-pane>
        <el-tab-pane label="メニュー・コース" name="tab3">
          <div>这里是 Tab 3 的内容</div>
        </el-tab-pane>
        <el-tab-pane label="写真" name="tab4">
          <div>这里是 Tab 4 的内容</div>
        </el-tab-pane>
      </el-tabs>
    </div>
  </div>
</template>

<script>
import {ref} from 'vue';
import {ElTabs, ElTabPane} from 'element-plus';
import First from  './page/first.vue';

export default {
  components: {
    ElTabs,
    ElTabPane,
    First,
  },
  setup() {
    const activeTab = ref("tab1");
    return {activeTab};
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  padding: 0 15px; /* 增加左右间隔 */
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
  color: white;
  font-size: 24px;
  background-color: rgba(0, 0, 0, 0.5);
  padding: 5px 10px;
  border-radius: 5px;
  text-align: center; /* 文字居中 */
}

.tabs-wrapper {
  display: flex;
  justify-content: center;
}

.custom-tabs {
  width: 80%; /* 将 Tabs 宽度设为页面宽度的 80% */
}

.el-tabs__nav {
  display: flex;
  justify-content: space-between; /* 改为 space-between */
  width: 100%; /* 确保导航条占满可用宽度 */
}

.el-tabs__item {
  flex: 1; /* 每个 Tab 项目均分宽度 */
  text-align: center;
}

.custom-tabs .el-tabs__item {
  color: brown; /* 设置未选中 Tab 的字体颜色 */
}

.custom-tabs .el-tabs__item.is-active {
  background-color: #797152; /* 设置选中 Tab 的背景颜色 */
  color: white; /* 设置选中 Tab 的字体颜色 */
}

.custom-tabs .el-tabs__active-bar {
  background-color: #797152; /* 设置活动条的颜色 */
}

.el-tabs--card > .el-tabs__header {
  border-bottom: none; /* 去掉卡片样式的底部边框 */
}
</style>
