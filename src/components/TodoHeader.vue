<template>
  <div class="wrapper">
    <div class="header">
      <div class="week">{{week}},</div>
      <div class="day">{{day}}th</div>
      <div class="count">12 Tasks</div>
    </div>
    <div class="month">{{month}}</div>
  </div>
</template>

<script>

export default {

  data() {
    return {
      day:'',
      week:'',
      month:''
    }
  },

  created() { 
    this.getDay();
    this.getWeek();
    this.getMonth();
  },

  methods: {
    getDay: function() {
      let day = new Date().getDate();
      this.day = day;
    },
    getWeek: function() {
      let weekList = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
      let thisDay = new Date().getDay();
      let week = weekList[thisDay];
      this.week = week;
    },
    getMonth: function() {
      let monthList = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'];
      let thisDay = new Date().getMonth();
      let month = monthList[thisDay];
      this.month = month;
    }
  }

};
</script>

<style scoped>
.wrapper {
  width:100%;
  height: 150px;
  border-bottom: solid 1px rgb(190, 190, 190);
  border-start-start-radius: 10px;
  border-start-end-radius: 10px;
  background-color: rgba(245, 255, 245, 0.822);
}
.header {
  display: flex;
  padding-top: 40px;
  padding-left: 40px;
  padding-right: 40px;
}
.week {
  font-size: 40px;
  font-weight: bold;
  color: rgb(65, 250, 188);
}
.day {
  font-size: 40px;
  margin-left: 10px;
  color: rgb(65, 250, 188);
}
.count {
  font-size: 20px;
  margin-top: 10px;
  margin-left: 150px;
  color: rgb(190, 210, 190)
}
.month {
  font-size: 20px;
  padding-left: 40px;
  color: rgb(190, 210, 190)
}
</style>