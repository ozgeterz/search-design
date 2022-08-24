<template>
  <div class="search-bar">
    <input
      type="text"
      v-model="search"
      class="search-bar-input"
      placeholder="search for a part-time job"
    />
    <button @click="searchJob" class="search-Job">Search Job</button>
  </div>
</template>

<script>
import { eventBus } from "@/main";
export default {
  name: "SearchBar",
  data: () => ({ search: "" }),
  methods: {
    searchJob() {
        eventBus.$emit("search-query", this.search)
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/scss/color.scss";
.search {
  &-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    gap: 10px;
    margin-bottom: 30px;
  }

  &-Job {
    display: flex;
    align-items: center;
    padding: 20px;
    color: #ffffff;
    width: 100%;
    height: 56px;
    background: #281a51;
    border-radius: 4px;
    cursor: pointer;
    font-size: 14px;
    flex: 2;
  }

  &-bar-input {
    border: none;
    flex: 9;
    width: 100%;
    height: 56px;
    font-size: 18px;
    border: 1px solid $snuff;
    border-radius: 4px;
    padding: 10px;
  }

  &-feather {
    padding-bottom: 2px;
    padding-left: 3px;
    padding-right: 9px;
  }
}
</style>
