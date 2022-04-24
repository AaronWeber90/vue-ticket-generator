<script>
export default {
  props: {
    ticketData: Object,
  },
};
</script>

<template>
  <aside class="aside">
    <div class="input-container">
      <label
        ><p>Header - background Color</p>
        <input type="color" v-model="ticketData.headerBg" />
      </label>
      <label
        ><p>Flight details - font Size</p>
        <input
          type="number"
          v-model="ticketData.detailsfontSize"
          min="10"
          max="20"
        />
      </label>
      <label
        ><p>Flight values - font Size</p>
        <input
          type="number"
          v-model="ticketData.valuesfontSize"
          min="10"
          max="20"
        />
      </label>
      <label
        ><p>Flight values - font color</p>
        <input type="color" v-model="ticketData.fontColor" />
      </label>
      <label
        ><p>Passenger name</p>
        <input
          type="text"
          v-model="ticketData.passengerName"
          placeholder="e.g. Max Mustermann"
          maxlength="15"
        />
      </label>
    </div>
  </aside>
</template>

<style scoped>
.input-container {
  display: flex;
  flex-direction: column;
  gap: 1.5em;
}

.input-container input {
  width: 100%;
}

.aside {
  background: #fff;
  flex: 1 1 30%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 5px 5px 30px rgba(0, 0, 0, 0.3);
  z-index: 1;
}

.aside p {
  font-weight: bold;
  margin-bottom: 0.5em;
}
</style>
