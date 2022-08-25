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
    svg:"./svg/car-back-side-seats-icon.svg"
},
{
  name:"property",
  svg:"./svg/homepage-icon.svg"
},
{
  name:"travel",
  svg:"./svg/plane-landing-icon.svg"
},
{
  name:"boat",
  svg:"./svg/warship-icon.svg"
},
{
  name:"mc",
  svg:"./svg/kick-scooter-icon.svg"
},
{
  name:"job",
  svg:"./svg/corporate-icon.svg"
},
{
  name:"economy",
  svg:"./svg/analytics-icon.svg"
},
{
  name:"holiday",
  svg:"./svg/car-back-side-seats-icon.svg"
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