<script setup>
import ImageComponent from "../image/ImageComponent.vue";
import notiImg from '@images/customs/img.png';
import notiImg2 from '@images/customs/img2.png';
import notiImg3 from '@images/customs/img3.jpg';
const props = defineProps({
  content: {
    type: Object,
    default: () => {}
  }
});
const emit = defineEmits(['handlePopupClose']);
const handlePopupClose = () => {
  emit('handlePopupClose');
};
</script>
<template>
  <div class="popup qr">
    <div class="popup-inner">
      <div class="popup-header">{{ props.content.title }}</div>
      <div class="popup-contents">
        <!-- <ImageComponent :src="notiImg" :aspectRatio="'521 / 361'" alt="" class="noti-image" /> -->
        <!-- <ImageComponent :src="notiImg2" :aspectRatio="'525 / 1346'" alt="" class="noti-image" /> -->
        <ImageComponent :src="notiImg3" :aspectRatio="'409 / 1202'" alt="" class="noti-image" />
      </div>
      <div class="popup-footer">
        <div class="btn-wrap">
          <button type="button" class="btn btn-confirm" @click="handlePopupClose">확인</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.popup.qr {
  width: 100%;
  height: 100%;
  @media (min-width: 768px) {
    max-width: 900px;

  }
}
.popup-inner {
  display: flex;
  flex-direction: column;
  height: 100%;
}
.popup-contents {
  padding: 20px;
  @media (min-width: 768px) {
    padding: 40px;
  }
  .noti-image {
    display: block;
    width: 100%;
  }
  .tx-description {
    font-size: 16px;
    text-align: center;
    @media (min-width: 768px) {
      font-size: 20px;
    }
  }
}
.popup-footer {
  padding: 0 20px 20px;
  @media (min-width: 768px) {
    padding: 0 40px 40px;
  }
}
</style>
