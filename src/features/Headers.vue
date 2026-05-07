<script setup>
</script>
<template>
  <header class="header">
    <div class="h-container">
      <div class="h-row h-row-align-center h-row-justify-center">
        <div class="h-col h-col-3 col-logo"><img src="@images/logo.svg" alt="Logo" /></div>
        <div class="h-col h-col-9 col-title">2026 CERAGEM VISION TOUR in SAPPORO</div>
      </div>
    </div>
  </header>
</template>
<style lang="scss" scoped>
.header {
  padding: 40px 0;
  @include breakpoint('m') {
    background-position: left top, right top;
  }
}
.col-logo {
  img {
    width: 100%;
    aspect-ratio: 1/1;
    border-radius: 100%;
    overflow: hidden;
  }
}
.col-title {
  font-size: 38px;
  font-weight: bold;
  text-shadow: 0 0 8px #fff;
  @include breakpoint('s') {
    font-size: 24px;
  }
  @include breakpoint('m') {
    font-size: 26px;
  }
  @include breakpoint('l') {
    font-size: 38px;
  }

}
</style>
