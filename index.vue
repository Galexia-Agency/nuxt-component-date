<style scoped>
.date {
  grid-row: span 3;
  grid-column: 1;
  margin-top: 8px;
  text-align: center
}
.day {
  display: grid;
  width: 65px;
  height: 40px;
  color: var(--dayTextColor);
  font-size: 1.5rem;
  font-style: italic;
  background-color: var(--dayBackgroundColor);
  place-items: center
}
.monthYear {
  width: 65px;
  height: 48px;
  margin-top: -1px;
  padding-top: 4px;
  color: var(--monthYearTextColor);
  background-color: var(--monthYearBackgroundColor);
  clip-path: polygon(0 0, 100% 0, 100% 100%, 50% 70%, 0 100%)
}
@media (max-width: 576px) {
  .date {
    margin-bottom: 1rem
  }
}
</style>
<template>
  <div
    class="date"
    :style="`
      --dayTextColor: ${dayTextColor};
      --dayBackgroundColor: ${dayBackgroundColor};
      --monthYearTextColor: ${monthYearTextColor};
      --monthYearBackgroundColor: ${monthYearBackgroundColor};
    `"
  >
    <div class="day" v-text="getDay(date)" />
    <div class="monthYear" v-text="`${getMonth(date)} '${getYear(date)}`" />
  </div>
</template>

<script>
export default {
  name: 'GalexiaNuxtComponentDate',
  props: {
    date: {
      type: Date,
      required: true
    },
    dayTextColor: {
      type: String,
      required: true
    },
    dayBackgroundColor: {
      type: String,
      required: true
    },
    monthYearTextColor: {
      type: String,
      required: true
    },
    monthYearBackgroundColor: {
      type: String,
      required: true
    }
  },
  methods: {
    getDay (date) {
      return date.getDate()
    },
    getMonth (date) {
      const monthArr = []
      monthArr[0] = 'Jan'
      monthArr[1] = 'Feb'
      monthArr[2] = 'Mar'
      monthArr[3] = 'Apr'
      monthArr[4] = 'May'
      monthArr[5] = 'Jun'
      monthArr[6] = 'Jul'
      monthArr[7] = 'Aug'
      monthArr[8] = 'Sep'
      monthArr[9] = 'Oct'
      monthArr[10] = 'Nov'
      monthArr[11] = 'Dec'
      return monthArr[date.getMonth()]
    },
    getYear (date) {
      return date.getFullYear().toString().substring(2)
    }
  }
}
</script>
