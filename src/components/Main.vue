<script>
export default {
  props: {
    ticketData: Object,
  },
};
</script>

<template>
  <main
    class="main"
    :style="{
      '--topbg': ticketData.headerBg,
      '--text-details-font-size': ticketData.detailsfontSize + 'px',
      '--text-values-font-size': ticketData.valuesfontSize + 'px',
      '--text-values-clr': ticketData.fontColor,
    }"
  >
    <div class="container">
      <!-- <div class="ticket basic">
        <p>Admit One</p>
      </div> -->
      <div class="ticket airline">
        <div class="top">
          <h1>boarding pass</h1>
          <div class="big">
            <p class="from">BWI</p>
            <p class="to"><i class="fas fa-arrow-right"></i> SAN</p>
          </div>
          <div class="top--side">
            <i class="fas fa-plane"></i>
            <p>Baltimore</p>
            <p>San Diego</p>
          </div>
        </div>
        <div class="bottom">
          <div class="column">
            <div class="row row-1">
              <p>
                <span class="ticket-details">Flight</span>
                <span class="ticket-value">AA2005</span>
              </p>
              <p class="row--right">
                <span class="ticket-details">Gate</span>
                <span class="ticket-value">B3</span>
              </p>
            </div>
            <div class="row row-2">
              <p>
                <span class="ticket-details">Boards</span>
                <span class="ticket-value">10:25 AM</span>
              </p>
              <p class="row--center">
                <span class="ticket-details">Departs</span>
                <span class="ticket-value">11:00 AM</span>
              </p>
              <p class="row--right">
                <span class="ticket-details">Arrives</span>
                <span class="ticket-value">1:05 PM</span>
              </p>
            </div>
            <div class="row row-3">
              <p>
                <span class="ticket-details">Passenger</span>
                <span class="ticket-value">{{ ticketData.passengerName }}</span>
              </p>
              <p class="row--center">
                <span class="ticket-details">Seat</span>
                <span class="ticket-value">11E</span>
              </p>
              <p class="row--right">
                <span class="ticket-details">Group</span>
                <span class="ticket-value">3</span>
              </p>
            </div>
          </div>
          <div class="bar--code"></div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap");

.main {
  flex: 1 1 70%;
  font-family: "Open Sans";
  min-height: 100%;
}
.main {
  --container-clr: #e0e2e8;
  --topbg: #ffcc05;
  --bottombg: #fff;
  --font: "Open Sans", sans-serif;
  --text-values-clr: #6c6c6c;
  --text-details-font-size: 16px;
  --text-values-font-size: 16px;
}

.container {
  background: var(--container-clr);
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.basic {
  display: none;
}

.airline {
  display: block;
  height: 575px;
  width: 270px;
  box-shadow: 5px 5px 30px rgba(0, 0, 0, 0.3);
  border-radius: 25px;
  z-index: 3;
}

.airline .top {
  height: 220px;
  background: var(--topbg);
  border-top-right-radius: 25px;
  border-top-left-radius: 25px;
}

.airline h1 {
  text-transform: uppercase;
  font-size: 12px;
  letter-spacing: 2;
  text-align: center;
  position: absolute;
  top: 30px;
  left: 50%;
  transform: translateX(-50%);
}

.airline .bottom {
  height: 355px;
  background: var(--bottombg);
  border-bottom-right-radius: 25px;
  border-bottom-left-radius: 25px;
}

.top .big {
  position: absolute;
  top: 100px;
  font-size: 65px;
  font-weight: 700;
  line-height: 0.8;
}

.top .from {
  color: var(--topbg);
  text-shadow: -1px 0 #000, 0 1px #000, 1px 0 #000, 0 -1px #000;
}

.top .to {
  position: absolute;
  left: 32px;
  font-size: 35px;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.top i {
  margin-top: 5px;
  margin-right: 10px;
  font-size: 15px;
}

.top--side {
  position: absolute;
  right: 35px;
  top: 110px;
  text-align: right;
}

.top--side i {
  font-size: 25px;
  margin-bottom: 18px;
}

.top--side p {
  font-size: 10px;
  font-weight: 700;
}

.top--side p + p {
  margin-bottom: 8px;
}

.bottom p {
  display: flex;
  flex-direction: column;
}

.bottom .ticket-details {
  font-weight: 400;
  font-size: var(--text-details-font-size);
  color: var(--text-details-clr);
}

.bottom .ticket-value {
  font-size: var(--text-values-font-size);
  font-weight: 700;
  color: var(--text-values-clr);
}

.column {
  margin: 0 auto;
  width: 80%;
  padding: 2rem 0;
}

.row {
  display: flex;
  justify-content: space-between;
}

.row--right {
  text-align: right;
}

.row--center {
  text-align: center;
}

.row-2 {
  position: relative;
}

.bottom .bar--code {
  height: 50px;
  width: 80%;
  margin: 0 auto;
  position: relative;
}

.bottom .bar--code::after {
  content: "";
  position: absolute;
  width: 6px;
  height: 100%;
  background: #000;
  top: 0;
  left: 0;
  box-shadow: 10px 0 #000, 30px 0 #000, 40px 0 #000, 67px 0 #000, 90px 0 #000,
    100px 0 #000, 180px 0 #000, 165px 0 #000, 200px 0 #000, 210px 0 #000,
    135px 0 #000, 120px 0 #000;
}

.bottom .bar--code::before {
  content: "";
  position: absolute;
  width: 3px;
  height: 100%;
  background: #000;
  top: 0;
  left: 11px;
  box-shadow: 12px 0 #000, -4px 0 #000, 45px 0 #000, 65px 0 #000, 72px 0 #000,
    78px 0 #000, 97px 0 #000, 150px 0 #000, 165px 0 #000, 180px 0 #000,
    135px 0 #000, 120px 0 #000;
}

.info {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: 10px;
  font-size: 14px;
  text-align: center;
  z-index: 1;
}

.info a {
  text-decoration: none;
  color: #000;
  background: var(--grey);
}
</style>
