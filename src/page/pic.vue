<template>
  <div>
    <hr class="divider" />
    <div class="icon-pic">
      お店からの写真(48件)
    </div>
    <p>1～48 件を表示 ／ 全 48 件</p>
    <div class="image-gallery">
      <div v-for="n in 48" :key="n" class="image-item">
        <img :src="images[n]" :alt="`Image ${n}`" @error="onImageError(n)" />
        <p class="description">{{ descriptions[n] }}</p>
      </div>
    </div>
    <hr class="divider" />
    <BasicDetail/>
  </div>
</template>

<script>
import BasicDetail from "@/page/comp/basicDetail.vue";
import { ref } from 'vue';


export default {
  name: 'Pic',
  components: {
    BasicDetail
  },
  setup() {
    // 使用 import.meta.glob 批量导入图片
    const imageModules = import.meta.glob('@/assets/tab4sets/*.jpg', { eager: true });
    const images = {};

    // 将文件路径按照顺序编号
    Object.keys(imageModules).forEach(key => {
      const match = key.match(/\/(\d+)\.jpg$/);
      if (match) {
        const index = parseInt(match[1], 10);
        images[index] = imageModules[key].default;
      }
    });

    const descriptions = ref({
      1: "内観 （by お店）",
      2: "外観 （by お店）",
      3: "青島ビール （by お店）",
      4: "揚げピーナッツ （by お店）",
      5: "（by お店）",
      6: "青島ビール （by お店）",
      7: "個室 （by お店）",
      8: "たたき胡瓜 （by お店）",
      9: "（by お店）",
      10: "茅台迎賓酒 （by お店）",
      11: "ザーサイ （by お店）",
      12: "（by お店）",
      13: "（by お店）",
      14: "茅台迎賓酒 （by お店）",
      15: "ネギチャーシュー （by お店）",
      16: "（by お店）",
      17: "豚耳 （by お店）",
      18: "（by お店）",
      19: "紹興酒一合 （by お店）",
      20: "チンジャオロース （by お店）",
      21: "宴会におすすめの個室 （by お店）",
      22: "二階堂 （by お店）",
      23: "（by お店）",
      24: "広々として店内 （by お店）",
      25: "（by お店）",
      26: "（by お店）",
      27: "（by お店）",
      28: "（by お店）",
      29: "（by お店）",
      30: "（by お店）",
      31: "（by お店）",
      32: "（by お店）",
      33: "（by お店）",
      34: "（by お店）",
      35: "（by お店）",
      36: "（by お店）",
      37: "（by お店）",
      38: "（by お店）",
      39: "（by お店）",
      40: "（by お店）",
      41: "（by お店）",
      42: "（by お店）",
      43: "（by お店）",
      44: "（by お店）",
      45: "（by お店）",
      46: "（by お店）",
      47: "（by お店）",
      48: "（by お店）",
    });

    return {
      images,
      descriptions
    };
  },
  methods: {
    onImageError(n) {
      console.error(`Failed to load image: ${n}`);
    }
  }
};
</script>

<style scoped>
.icon-pic::before {
  font-size: 1.8rem;
  font-family: 'Tabelog Glyph';
  content: '\f6ac';
}

.icon-pic {
  color: #ff9600;
  font-weight: bold;
  background-color: #fff;
}

.image-gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 16px; /* 控制图片间距 */
}

.image-item {
  width: calc(100% / 4 - 16px); /* 每行显示6张图片 */
  box-sizing: border-box;
  text-align: center;
}

.image-item img {
  width: 100%;
  height: auto;
  border-radius: 8px; /* 圆角效果 */
}

.description{
  padding: 4px;
  color: #949499;
  font-size: 86%;
}
</style>
