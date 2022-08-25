<template>
  <cardbtn @click="click" class="btn" :class="[color]">
    <slot />
  </cardbtn>
</template>
<script>
export default {
  methods: {
    click() {
      this.$emit("click");
    },
  },
  props: {
    color: {
      type: String,
    },
 },
};
</script>
<style lang="scss" scoped>
@import "../assets/scss/color.scss";
.btn {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 5px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 500;
  font-size: 18px;
 &.furniture {
    background-color: $Furniture;
 }
 &.property {
    background-color: $Property;
 }
 &.job {
    background-color: $Job;
 }
 &.travel {
    background-color: $Travel;
 }
 &.boat {
    background-color: $Boat;
 }
 &.mc {
    background-color: $MC;
 }
 &.economy {
    background-color: $Economy;
 }
 &.holiday {
    background-color: $Holiday;
 }
  }
</style>