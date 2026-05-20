<script setup>
</script>
<template>
  <header class="header">
    <div class="h-container">
      <div class="h-row h-row-align-center h-row-justify-center">
        <div class="h-col h-col-8 h-col-sm-10 h-col-md-8">
          <div class="logo">
            <img src="@images/header-bg-text.png" alt="Logo" />
          </div>
        </div>
      </div>
    </div>
  </header>
</template>
<style lang="scss" scoped>
.header {
  background-image: url(@images/header-bg-pattern.png);
  background-size: 140px 140px;
  background-position: center;
  .h-container {
    background-color: #fff;
  }
}
.logo {
  width: 100%;
  padding: 60px 0;
  text-align: center;
  img {
    width: 100%;
    aspect-ratio: 386 / 113;
  }
}
@include breakpoint('s') {
  .header {
    background-size: 80px 80px;
    .h-container {
      background-image: linear-gradient(to right, rgba(255,255,255,0), rgba(255,255,255,1) 12%, rgba(255,255,255,1) 88%, rgba(255,255,255,0));
      background-color: transparent;
      .h-row {
        .h-col {
          // background-color: #fff;
        }
      }
    }
  }
}
</style>
