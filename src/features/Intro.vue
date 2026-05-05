<script setup>
import { ref, onMounted } from 'vue';
import introLogo from '@images/intro/logo.png';

const isVisible = ref(false); // 인트로 표시 여부
const INTRO_KEY = 'hide_intro_until';
const DAY_IN_MS = 24 * 60 * 60 * 1000;

// const closeIntro = () => {
//   isVisible.value = false;
//   // 로컬스토리지 저장은 닫기 시작할 때 바로 수행
//   const expiryDate = new Date().getTime() + DAY_IN_MS;
//   localStorage.setItem(INTRO_KEY, expiryDate.toString());
// };

// onMounted(() => {
//   const hiddenUntil = localStorage.getItem(INTRO_KEY);
//   const now = new Date().getTime();

//   if (!hiddenUntil || now > parseInt(hiddenUntil)) {
//     isVisible.value = true;

//     // 3초 후에 자동으로 닫기 (Transition이 fade-out을 알아서 처리함)
//     setTimeout(() => {
//       if (isVisible.value) closeIntro();
//     }, 3000);
//   }
// });

onMounted(() => {
  isVisible.value = true;

  // 3초 후에 자동으로 닫기 (Transition이 fade-out을 알아서 처리함)
  setTimeout(() => {
    isVisible.value = false;
  }, 3000);
});


defineExpose({ isVisible });
</script>

<template>
  <!-- name="intro-fade"로 지정 -->
  <Transition name="intro-fade">
    <div v-if="isVisible" class="intro-section">
      <div class="h-dimm"></div>
      <div class="h-container h-full-height">
        <div class="h-row h-row-direction-column h-row-justify-center h-row-gap-40 h-full-height">
          <div class="h-col h-col-12 col-logo entry-animation delay-1">
            <img :src="introLogo" alt="unicity" />
          </div>
          <div class="h-col h-col-12 col-text entry-animation delay-2">
            2026 UNICITY INTERNATIONAL<br />
            BIOS LIFE LEADERSHIP TRIP<br />
            IN SAPPORO
          </div>
        </div>
      </div>
    </div>
  </Transition>
</template>

<style lang="scss" scoped>
@keyframes fadeIn {
  from {
    transform: translateY(30px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.intro-section {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background-image: url('@images/intro/bg.jpg');
  background-size: cover;
  background-position: center;
  z-index: 1000000;
}

/* --- Transition 전용 스타일 --- */
/* 나갈 때(Leave) 2초 동안 페이드 아웃 */
.intro-fade-leave-active {
  transition: opacity 2s ease-in-out;
}

/* 나가는 끝 지점 상태 */
.intro-fade-leave-to {
  opacity: 0;
}

/* 내부 요소 애니메이션 (기존 isActive 대신 사용) */
.entry-animation {
  opacity: 0;
  animation: fadeIn 1s forwards;
  &.delay-1 { animation-delay: 0.5s; }
  &.delay-2 { animation-delay: 1.5s; }
}

/* 나머지 기존 스타일 유지 */
.col-logo {
  img { width: 80%; max-width: 580px; }
  text-align: center;
}
.col-text {
  font-size: clamp(2.4rem, 2.8vw, 4.4rem);
  font-weight: bold;
  color: #fff;
  text-align: center;
}
</style>