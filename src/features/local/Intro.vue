<script setup>
import { ImageComponent } from '@/components/image';
</script>

<template>
  <div class="intro-container">
    <h2 class="section-title">삿포로 (SAPPORO)</h2>

    <ImageComponent :src="'/assets/images/local/intro/bg.jpg'" alt="삿포로 이미지" class="local-image mb40" />

    <div class="info-grid">
      <div class="info-card">
        <h3 class="info-card-title">🕐 한국과의 시차</h3>
        <p>한국과 동일합니다.<br /><small>(예. 한국: 오전 10시 / 일본: 오전 10시)</small></p>
      </div>

      <div class="info-card">
        <h3 class="info-card-title">🌤️ 지역 날씨</h3>
        <p>삿포로의 8월은 여름철로, <strong>비교적 습도가 낮고 쾌적한 날씨</strong>가 이어집니다.평균 최고 기온은 약 <strong>26~28°C</strong>, 평균 최저 기온은 약 <strong>20~22°C</strong> 수준이며, 한낮에는 다소 덥게 느껴질 수 있습니다. 다만 아침·저녁으로는 비교적 선선할 수 있습니다.</p>
      </div>

      <div class="info-card">
        <h3 class="info-card-title">👕 옷차림</h3>
        <p><strong>낮</strong>: 반팔 티셔츠, 얇은 셔츠 등 가벼운 여름 복장 추천</p>
        <p><strong>저녁</strong>: 자외선 차단 및 실내 냉방 대비를 위해 얇은 가디건 또는 가벼운 겉옷을 준비하시기 바랍니다.</p>
      </div>

      <div class="info-card">
        <h3 class="info-card-title">💰 화폐</h3>
        <p>일본 화폐인 <strong>엔화(JPY)</strong>를 사용합니다.</p>
        <p>카드 결제가 매우 보편적이지만, 일부 소규모 식당·시장·간식/노점은 현금이 필요할 수 있어 <strong>소액 현금을 준비하시는 것을 추천</strong>드립니다.</p>
      </div>

      <div class="info-card">
        <h3 class="info-card-title">⚡ 전압</h3>
        <p>일본 전압은 <strong>100V, 50Hz</strong>이며, 한국(220V)과 달라 돼지코 형태(일본/미국형 플러그) 어댑터가 필요합니다.</p>
      </div>

      <div class="info-card">
        <h3 class="info-card-title">📋 여권/VISA</h3>
        <p>여권은 유효기간이 충분히 남아 있어야 하며, 원활한 출입국을 위해 6개월 이상 잔여를 권장합니다.</p>
        <p>대한민국 여권 소지자는 관광 목적으로 최대 <strong>90일간 무비자 체류</strong>가 가능합니다.</p>
      </div>

      <div class="info-card warning">
        <h3 class="info-card-title">⚠️ 주의 사항</h3>
        <ul>
          <li>일본은 전반적으로 치안이 안전한 편이나, 관광지/번화가에서는 소지품 분실·도난에 유의하시기 바랍니다.</li>
          <li>8월은 자외선이 강하고 낮 기온이 높아질 수 있으므로,모자·선크림·휴대용 선풍기 등을 준비하시는 것을 추천드립니다. 또한 간헐적으로 비가 내릴 수 있어 작은 우산이나 우비를 준비하시면 편리합니다.도로 횡단 시 신호 준수 및 자전거/차량 통행에 유의 바랍니다.</li>
        </ul>
      </div>
    </div>
  </div>
</template>