<template>
  <div id="app">
    <JobList :jobList="filterBySearch"/>
  </div>
</template>

<script>
import JobList from './components/JobList.vue';
import { eventBus } from "@/main";
export default {
    components: { JobList },
      data: () => ({ jobList:[{
    name:"furniture",
    svg:"../svg/car-back-side-seats-icon.svg"
},
{
  name:"property",
  svg:"../svg/analytics-icon.svg"
},
{
  name:"travel",
  svg:"../svg/analytics-icon.svg"
},
{
  name:"boat",
  svg:"../svg/analytics-icon.svg"
},
{
  name:"mc",
  svg:"../svg/analytics-icon.svg"
},
{
  name:"job",
  svg:"../svg/analytics-icon.svg"
},
{
  name:"economy",
  svg:"../svg/analytics-icon.svg"
},
{
  name:"holiday",
  svg:"../svg/analytics-icon.svg"
}
  ],
  data:""
   }),
   methods:{ filter: function (obj) {
      return obj.name.includes(this.data);
    }}, 
    created() {
    eventBus.$on("search-query", (data) => {
      this.data=data;
    });
    
  },
    computed:{filterBySearch:function(){
    return this.jobList.filter(this.filter);
    }}
}
</script>
<style>
*{
  margin:0;
  padding: 0;
  box-sizing: border-box;
}
</style>