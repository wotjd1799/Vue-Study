<template>
  <div class="hdWrap">
    <div class="hd">
      <div class="ndHdWrap">
        <div class="week">{{week}},</div>
        <div class="day">{{day}}{{th}}</div>
      </div>
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
      month:'',
      th:''
    }
  },

  created() { 
    this.getDay();
    this.getWeek();
    this.getTh();
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
    getTh: function() {
      if (this.day == 1 || this.day == 21){
        this.th = 'st'
      }
      else if (this.day == 2 || this.day == 22){
        this.th = 'nd'
      }
      else if (this.day == 3 || this.day == 23){
        this.th = 'rd'
      }
      else {
        this.th = 'th'
      }
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
.hdWrap {
  width:100%;
  height: 149px;
  border-bottom: solid 1px rgb(190, 190, 190);
  border-start-start-radius: 10px;
  border-start-end-radius: 10px;
  background-color: rgba(245, 255, 245, 0.822);
}
.ndHdWrap {
  display: flex;
  width: 230px;
}
.hd {
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
  margin-top: 20px;
  margin-left: 180px;
  color: rgb(190, 210, 190)
}
.month {
  font-size: 20px;
  padding-left: 40px;
  color: rgb(190, 210, 190)
}
</style>