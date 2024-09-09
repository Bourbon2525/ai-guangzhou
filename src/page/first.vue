<template>
  <video autoplay controls class="video">
    <source src="../assets/tab1sets/intro.mp4" type="video/mp4" />
    Your browser does not support the video tag.
  </video>
  <hr class="divider" />
  <div class="first-container">
    <img class="large-image" src="../assets/tab1sets/mapotofu.jpg" alt="大图片" />
    <div class="highlighted-text">
      ワテラス前、淡路町駅と小川町駅から徒歩1分。熱々の石鍋四川麻婆豆腐は牛バラの旨味がたっぷり
    </div>
    <div class="normal-text">
      淡路町駅と小川町駅から徒歩1分に構える【多福楼 お茶の水店】。「石鍋四川麻婆豆腐」やまん丸の唐揚げがメディアでも話題を集めた人気中華料理店です！麻婆豆腐は熱くて辛いだけでなく、中国各地から仕入れた香辛料や調味料、漢方と牛バラから抽出した油も入って旨味たっぷり。唐揚げもひと口サイズで、女性にも好評です♪御茶ノ水、新御茶ノ水、神田、秋葉原の各駅からも徒歩圏内。アクセスの良い当店で美味しいひと時を！!
    </div>
  </div>
  <hr class="divider" />
  <BasicDetail/>
</template>

<script>
import BasicDetail from "@/page/comp/basicDetail.vue";
export default {
  name: 'First',
  components: {
    BasicDetail
  },
};
</script>

<style>
.first-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.large-image {
  width: 100%;
  height: auto;
  max-width: 600px; /* 根据需要调整最大宽度 */
}

.highlighted-text {
  font-size: 20px;
  font-weight: bold;
  color: #333;
  margin-top: 20px;
  text-align: left;
}

.normal-text {
  font-size: 16px;
  color: #666;
  margin-top: 10px;
  text-align: left;
}

.video {
  width: 100%;
  height: auto;
  max-width: 800px; /* Adjust as needed */
  display: block;
  margin: 0 auto;
}
</style>
