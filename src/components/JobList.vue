<template>
  <div class="search-container">
    <div class="reactangle-2"></div>
    <div class="content">
      <SearchBar />
      <div class="cards">
        <CardsButton
          v-for="item in jobList"
          :key="item.name"
          :color="[item.name]"
          ><img :src="item.svg" />{{ item.name }}</CardsButton
        >
      </div>
    </div>
  </div>
</template>
<script>
import CardsButton from "./CardsButton.vue";
import SearchBar from "./SearchBar.vue";

export default {
  name: "JobList",
  components: {
    CardsButton,
    SearchBar,
  },
  props: { jobList: { type: Array } },
  methods: {},
};
</script>
<style lang="scss" scoped>
.search-container {
  position: relative;
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #f7f4ff;
  padding: 73px;
}
.reactangle-2 {
  position: absolute;
  width: 421px;
  height: 613px;
  background: #efebfd;
  border-radius: 31px;
}
.mc-btn {
  background: #ffffff;
  border: 1px solid #dbd5ec;
  box-shadow: 0px 14px 16px rgba(41, 11, 128, 0.1);
}
.content {
  width: 640px;
  height: 464px;
  padding: 73px;
  background: #ffffff;
  box-shadow: 0px 14px 52px -20px #8675b4;
  border-radius: 24px;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: space-between;
  z-index: 1;
}
.cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(2, 1fr);
  grid-gap: 16px;
  width: 100%;
  height: 100%;
}
.svg {
  padding-top: 20px;
  width: 40px;
  height: 40px;
}
.svg-search {
  padding-right: 5px;
  width: 20px;
}
</style>
