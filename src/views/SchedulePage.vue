<script setup>
import { ref } from "vue";
import { ImageComponent } from '@/components/image';

const scheduleInfo = ref([
  {
    daparture: "2026-08-19",
    return: "2026-08-21",
    flight: {
      departure: {
        airline: "인천 2터미널 출발 - 대한항공 탑승",
        flightNumber: "KE 765",
        departureAirport: "인천 (ICN)",
        departureTime: "10:35",
        arrivalAirport: "삿포로 (CTS)",
        arrivalTime: "13:25"
      },
      return: {
        airline: "신치토세 국제공항 출발 - 대한항공",
        flightNumber: "KE 766",
        departureAirport: "삿포로 (CTS)",
        departureTime: "14:50",
        arrivalAirport: "인천 (ICN)",
        arrivalTime: "17:55"
      },
    },
    dates: {
      day1: {
        date: "2026-08-19 (수)",
        title: "삿포로 도착 후 시내 관광",
        activities: {
          common: "시코츠호 방문, 타누키코지 도보투어"
        }
      },
      day2: {
        date: "2026-08-20 (목)",
        title: "삿포로 관광",
        activities: {
          common: "오타루 운하 및 오르골당 방문, 북해도 신궁, 구 훗카이도 도청사, 오도리 공원 탐방",
        }
      },
      day3: {
        date: "2026-08-21 (금)",
        title: "체크아웃 > 공항이동",
        activities: {}
      }
    }
  }
]);

</script>
<template>
  <div class="schedule-page">
    <div class="h-container">
      <div class="h-row">
        <div class="h-col h-col-12">
          <div class="schedule-section">
            <!-- 1일차: 출발 -->
            <h2 class="schedule-title">8월 19일 출발</h2>
            <div class="box-wrap">
              <div class="box-title">미팅 안내</div>
              <div class="box-content">
                <div class="h-row">
                  <div class="h-col h-col-12 h-col-md-6">
                    <p><strong>미팅 포인트</strong></p>
                    <ul class="list-check">
                      <li>인천국제공항 제 2터미널 3번 출입구 안쪽</li>
                    </ul>
                  </div>
                  <div class="h-col h-col-12 h-col-md-6">
                    <p><strong>미팅 시간:</strong></p>
                    <ul class="list-check">
                      <li>2026년 8월 19일(수) 07시 30분</li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
            <div class="h-row">
              <div class="h-col h-col-12 ">
                <div class="flight-info">
                  <div class="flight-area">{{ scheduleInfo[0].flight.departure.airline }}</div>
                  <div class="flight-route">
                    <div class="city">{{ scheduleInfo[0].flight.departure.departureAirport }}<br />10:35</div>
                    <div class="flight-code">{{ scheduleInfo[0].flight.departure.flightNumber }}</div>
                    <div class="city">{{ scheduleInfo[0].flight.departure.arrivalAirport }}<br />13:25</div>
                  </div>
                  <!-- <div class="hotel-name">숙소: SAPPORO GRAND HOTEL</div> -->
                </div>
              </div>
            </div>
            <!-- 1일차 -->
            <div class="day-card">
              <div class="day-header">
                <div class="day-number">Day 1</div>
                <div class="day-date">{{ scheduleInfo[0].dates.day1.date }}</div>
                <div class="day-title">{{ scheduleInfo[0].dates.day1.title }}</div>
              </div>
              <div class="day-activities">
                <div class="activity-section">
                  <div class="activity-description">{{ scheduleInfo[0].dates.day1.activities.common }}</div>
                  <div class="h-row h-row-mb">
                    <div class="h-col h-col-12 h-col-md-6">
                      <ImageComponent :src="'/assets/images/schedule/day1/img1.jpg'" alt="시코츠호" />
                    </div>
                    <div class="h-col h-col-12 h-col-md-6">
                      <ImageComponent :src="'/assets/images/schedule/day1/img2.jpg'" alt="타누키코지 도보투어" />
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- 2일차 -->
            <div class="day-card">
              <div class="day-header">
                <div class="day-number">Day 2</div>
                <div class="day-date">{{ scheduleInfo[0].dates.day2.date }}</div>
                <div class="day-title">{{ scheduleInfo[0].dates.day2.title }}</div>
              </div>
              <div class="day-activities">
                <div class="h-row h-row-mb">
                  <div class="h-col h-col-12">
                    <div class="activity-section">
                      <span class="section-badge">유니팀</span>
                      <div class="activity-description">{{ scheduleInfo[0].dates.day2.activities.common }}</div>
                      <div class="h-row h-row-mb">
                        <div class="h-col h-col-12 h-col-md-6">
                          <ImageComponent :src="'/assets/images/schedule/day2/img1.jpg'" alt="오타루 운하 및 오르골당 관광" />
                        </div>
                        <div class="h-col h-col-12 h-col-md-6">
                          <ImageComponent :src="'/assets/images/schedule/day2/img2.jpg'" alt="북해도 신궁" />
                        </div>
                        <div class="h-col h-col-12 h-col-md-6">
                          <ImageComponent :src="'/assets/images/schedule/day2/img3.jpg'" alt="구 훗카이도 도청사" />
                        </div>
                        <div class="h-col h-col-12 h-col-md-6">
                          <ImageComponent :src="'/assets/images/schedule/day2/img4.jpg'" alt="오도리 공원" />
                        </div>
                      </div>
                      <div class="section-info">🍴 중식(스시 정식) / 석식(호텔만찬)</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- 3일차 -->
            <div class="day-card">
              <div class="day-header nomargin">
                <div class="day-number">Day3</div>
                <div class="day-date">{{ scheduleInfo[0].dates.day3.date }}</div>
                <div class="day-title">{{ scheduleInfo[0].dates.day3.title }}</div>
              </div>
            </div>
            <!-- 5일차: 복귀 -->
            <div class="h-row">
              <div class="h-col h-col-12">
                <div class="flight-info return">
                  <div class="flight-area">{{ scheduleInfo[0].flight.return.airline }}</div>
                  <div class="flight-route">
                    <div class="city">{{ scheduleInfo[0].flight.return.departureAirport }}<br />{{ scheduleInfo[0].flight.return.departureTime }}</div>
                    <div class="flight-code">{{ scheduleInfo[0].flight.return.flightNumber }}</div>
                    <div class="city">{{ scheduleInfo[0].flight.return.arrivalAirport }}<br />{{ scheduleInfo[0].flight.return.arrivalTime }}</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.schedule-page {
  padding: 40px 10px;
  @include breakpoint('m') {
    padding: 60px 20px 80px;
  }

  .schedule-title {
    font-size: 28px;
    font-weight: 700;
    color: #333;
    margin-bottom: 32px;
    text-align: center;

    @include breakpoint('m') {
      font-size: 36px;
      margin-bottom: 48px;
    }
  }

  .meeting-info {
    background: white;
    border-radius: 12px;
    padding: 24px;
    margin-bottom: 32px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);

    @include breakpoint('m') {
      padding: 32px;
    }

    .info-title {
      font-size: 18px;
      font-weight: 600;
      color: var(--common-color-highlight);
      margin-bottom: 16px;
    }

    .info-content {
      font-size: 15px;
      color: #555;

      strong {
        color: #333;
        font-weight: 600;
      }
    }
  }

  // Flight Info
  .flight-info {
    background-image: var(--common-bg-gradient);
    color: white;
    border-radius: 12px;
    padding: 24px;
    margin-bottom: 32px;
    text-align: center;

    @include breakpoint('m') {
      padding: 32px;
    }

    .flight-area {
      font-size: 16px;
      color: #fff;
      margin-bottom: 12px;
    }

    .flight-route {
      display: flex;
      justify-content: space-around;
      align-items: center;
      gap: 16px;
      flex-wrap: wrap;
      margin-bottom: 12px;
      @media (max-width: 370px) {
        flex-direction: column;
      }
      .city {
        font-size: 20px;
        font-weight: 700;

        @include breakpoint('m') {
          font-size: 24px;
        }
      }

      .flight-code {
        font-size: 18px;
        opacity: 0.9;
        @media (max-width: 370px) {
          padding: 10px 0;
          border-top: 1px solid #fff;
          border-bottom: 1px solid #fff;
        }
      }
    }

    .hotel-name {
      font-size: 16px;
      margin-top: 16px;
      opacity: 0.95;
    }

    &.return {
      background: #333;

      .flight-area {
        color: #aaa;
      }
    }
  }

  // Day Cards
  .day-card {
    background: white;
    border-radius: 12px;
    padding: 24px;
    margin-bottom: 24px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
    transition: transform 0.3s ease, box-shadow 0.3s ease;

    @include breakpoint('m') {
      padding: 32px;
    }

    &:hover {
      transform: translateY(-4px);
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
    }

    .day-header {
      border-left: 4px solid var(--common-color-highlight);
      padding-left: 16px;
      margin-bottom: 20px;

      .day-number {
        font-size: 14px;
        color: var(--common-color-highlight);
        font-weight: 600;
        margin-bottom: 4px;
      }

      .day-date {
        font-size: 20px;
        font-weight: 700;
        color: #333;

        @include breakpoint('m') {
          font-size: 24px;
        }
      }

      .day-title {
        font-size: 16px;
        color: #666;
        margin-top: 8px;
      }
    }

    .day-activities {
      .activity-description {
        font-size: 12px;
        padding: 24px;
        border: 1px solid #e0e0e0;
        border-radius: 8px;
        background-color: var(--common-bg-color);
        transition: box-shadow 0.3s ease;
        margin-bottom: 20px;
        @include breakpoint('m') {
          font-size: 14px;
        }
      }
      .activity-section {
        margin-bottom: 20px;

        &:last-child {
          margin-bottom: 0;
        }

        .section-badge {
          display: inline-block;
          background: #e3f2fd;
          color: #1976d2;
          padding: 6px 12px;
          border-radius: 6px;
          font-size: 13px;
          font-weight: 600;
          margin-bottom: 12px;
        }

        .activity-list {
          list-style: none;
          padding: 0;
          margin: 0;

          li {
            padding: 8px 0 8px 24px;
            position: relative;
            font-size: 15px;
            color: #555;

            &::before {
              content: '•';
              position: absolute;
              left: 0;
              color: var(--common-color-highlight);
              font-size: 18px;
            }
          }
        }
        .section-info {
          background: #f8f9fa;
          border-radius: 8px;
          padding: 12px 16px;
          margin-top: 12px;
          font-size: 16px;
          color: #666;
          border-left: 3px solid #ffc107;
        }
      }
    }
  }


  // Flight Info Return
  .flight-info.return {
    background: #333;
    margin-top: 40px;

    .info-title {
      font-size: 16px;
      color: #aaa;
      margin-bottom: 12px;
      text-transform: uppercase;
      letter-spacing: 1px;
    }
  }

  // Common Activities
  .common-activities {
    margin-top: 16px;
    padding-top: 16px;
    border-top: 1px solid #eee;
  }
}
</style>
