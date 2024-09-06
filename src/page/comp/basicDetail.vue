<template>
  <div class="basic-detail">
    <div class="table-title">
      <span class="title-marker"></span>
      店舗基本情報
    </div>
    <table class="custom-table">
      <tbody>
      <tr>
        <td class="highlighted-cell">店名</td>
        <td>多福楼 御茶ノ水店</td>
      </tr>
      <tr>
        <td class="highlighted-cell">多福楼 御茶ノ水店</td>
        <td>右侧内容</td>
      </tr>
      <!-- 添加更多行 -->
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'BasicDetail',
};
</script>

<style>
.basic-detail {
  padding: 20px;
}

.table-title {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 10px;
  position: relative;
}

.title-marker {
  display: inline-block;
  width: 2px;
  height: 24px;
  background-color: #333;
}

.custom-table {
  width: 100%;
  border-collapse: collapse;
}

.custom-table td {
  padding: 10px;
  border-top: 1px solid #ccc;
  border-bottom: 1px solid #ccc;
}

.highlighted-cell {
  background-color: #FAF8F5; /* 浅棕色背景 */
  font-weight: bold;
  color: #333;
}
</style>
