<script setup>
import SideBar from "./components/Sidebar.vue";
import Main from "./components/Main.vue";
</script>

<script>
export default {
  data() {
    return {
      ticketData: {
        headerBg: "#ffcc05",
        detailsfontSize: 14,
        valuesfontSize: 14,
        fontColor: "#000000",
        passengerName: "",
      },
    };
  },
};
</script>

<template>
  <div class="wrapper">
    <SideBar :ticketData="ticketData" />
    <Main :ticketData="ticketData" />
  </div>
</template>

<style>
@import "./assets/base.css";

.wrapper {
  display: flex;
  flex-direction: row;
  min-height: 100vh;
}
</style>
