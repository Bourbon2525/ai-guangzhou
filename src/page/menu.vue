<template>
  <hr class="divider"/>
  <!-- Tabs with three options -->
  <el-tabs v-model="activeName">
    <el-tab-pane label="料理(89)" name="3-1">
      <Food/>
    </el-tab-pane>
    <el-tab-pane label="ドリンク(101)" name="3-2">
      <Drink/>
    </el-tab-pane>
    <el-tab-pane label="ランチ(10)" name="3-3">
      <Lunch/>
    </el-tab-pane>
  </el-tabs>
  <hr class="divider"/>
  <BasicDetail/>
</template>

<script>
import BasicDetail from "@/page/comp/basicDetail.vue";
import Food from "@/page/comp/food.vue";
import Drink from "@/page/comp/drink.vue";
import Lunch from "@/page/comp/lunch.vue";

export default {
  name: 'Menu',
  components: {
    Lunch,
    Drink,
    Food,
    BasicDetail
  },
  props: {
    defaultTab: {
      type: String,
      default: '3-1'
    }
  },
  data() {
    return {
      activeName: this.defaultTab
    };
  },
  watch: {
    defaultTab(newVal) {
      this.activeName = newVal;
    }
  },
};
</script>

<style>
.el-tabs__item {
  padding: 12px 24px; /* Increase padding */
  min-width: 200px;
}
</style>
