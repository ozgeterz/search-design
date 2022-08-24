<template>
  <div id="app">
    <JobList />
  </div>
</template>

<script>
import JobList from './components/JobList.vue';
export default {
    components: { JobList }
}
</script>
<style>
*{
  margin:0;
  padding: 0;
  box-sizing: border-box;
}
</style>