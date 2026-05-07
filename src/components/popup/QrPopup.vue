<script setup>
import ImageComponent from "../image/ImageComponent.vue";
import qrCode from '@images/local/airport/qr.png';
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
      <div class="popup-contents">
        <ImageComponent :src="qrCode" alt="" class="qr-image" />
        <div class="tx-description"><pre>{{ props.content.description }}</pre></div>
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
  @include breakpoint('m') {
    max-width: 500px;

  }
}
.popup-contents {
  padding: 20px;
  @include breakpoint('m') {
    padding: 40px;
  }
  .qr-image {
    width: 100%;
    display: block;
    margin-bottom: 20px;
    @include breakpoint('m') {
      margin-bottom: 40px;
    }
  }
  .tx-description {
    font-size: 16px;
    text-align: center;
    @include breakpoint('m') {
      font-size: 20px;
    }
  }
}
.popup-footer {
  padding: 0 20px 20px;
  @include breakpoint('m') {
    padding: 0 40px 40px;
  }
}
</style>
