<template>
  <hr class="divider" />
  <div class="highlighted-title">座席一覧</div>

  <div class="table-title">
    <span class="title-marker"></span>
    半個室
  </div>
  <div class="image-container">
    <div class="image-item">
      <img src="../assets/tab2sets/pic1-left.jpg" alt="半個室1">
      <p class="image-caption">全席可動式の座席。利用する人数に合わせて座席の移動が可能、半個室にもなります</p>
    </div>
    <div class="image-item">
      <img src="../assets/tab2sets/pic1-right.jpg" alt="半個室2">
      <p class="image-caption"></p>
    </div>
  </div>

  <div class="table-title">
    <span class="title-marker"></span>
    完全個室
  </div>
  <div class="image-container">
    <div class="image-item">
      <img src="../assets/tab2sets/pic2.jpg" alt="完全個室1">
      <p class="image-caption">大きなガラス張りの店内。明貸切は25名～40名ご利用ＯＫ！</p>
    </div>
  </div>

  <div class="table-title">
    <span class="title-marker"></span>
    テーブル席
  </div>
  <div class="image-container">
    <div class="image-item">
      <img src="../assets/tab2sets/pic3-left.jpg" alt="テーブル席1">
      <p class="image-caption">全席可動式の座席。利用する人数に合わせて座席の移動が可能、半個室にもなります</p>
    </div>
    <div class="image-item">
      <img src="../assets/tab2sets/pic3-right.jpg" alt="テーブル席2">
      <p class="image-caption"></p>
    </div>
    <div class="image-item">
      <img src="../assets/tab2sets/pic3-bot.jpg" alt="テーブル席3">
      <p class="image-caption"></p>
    </div>
  </div>
  <hr class="divider" />
  <BasicDetail/>
</template>

<script>
import BasicDetail from "@/page/comp/basicDetail.vue";

export default {
  name: 'Seat',
  components: {
    BasicDetail
  },
};
</script>

<style scoped>
.highlighted-title {
  font-weight: bold;
  color: #333;
}

.image-container {
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 20px;
  justify-content: space-between;
}

.image-item {
  margin: 0 80px;
  text-align: center;
}

.image-item img {
  max-width: 100%;
  height: auto;
}

.image-caption {
  margin-top: 10px;
  font-size: 14px;
  color: #666;
  min-height: 20px; /* Adjust this value as needed */
  max-width: 320px;
}

.title-marker{
  margin-left: 50px;
}
</style>
