<script setup>
const props = defineProps({
  src: {
    required: true
  },
  alt: {
    type: String,
    default: ""
  },
  altPosition: {
    type: String,
    default: "bottom"
  },
  aspectRatio: {
    type: String,
    default: "4 / 3"
  }
});
</script>

<template>
  <div class="image-component" :style="`aspect-ratio: ${props.aspectRatio}`">
    <div class="image-frame">
      <div class="image-element" :style="`background-image: url(${props.src})`"/>
    </div>
    <div v-if="props.alt" class="image-alt" :class="`image-alt-${props.altPosition}`">{{ props.alt }}</div>
  </div>
</template>
