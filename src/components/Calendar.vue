<template>
  <div class="m-auto">
    <h1 class="text-2xl text-center my-2">Vue Calendar</h1>
    <section class="mx-2 flex justify-between">
      <h2 class="font-bold">{{currentMonthName}}</h2>
      <h2 class="font-bold">{{currentYear}}</h2>
    </section>
    <section class="flex">
      <p class="text-center my-2" style="width: 14.28%" v-for="day in days" :key="day">{{ day }}</p>
    </section>
    <section class="flex flex-wrap">
      <p class="text-center" style="width: 14.28%" v-for="num in startDay()" :key="num"></p>
      <p class="text-center"
        style="width: 14.28%"
        v-for="num in daysInMonth()"
        :key="num"
        :class="currentDate(num) && 'bg-blue-800 text-white rounded-xl'"
      >
        {{num}}
      </p>
    </section>
    <section class="flex justify-between my-4">
      <button class="px-2 border rounded" @click="previous">Prev</button>
      <button class="px-2 border rounded" @click="next">Next</button>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentMonth: new Date().getMonth() + 1,
      currentYear: new Date().getFullYear(),
      days: ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat']
    }
  },
  methods: {
    next() {
      if(this.currentMonth === 12){
        this.currentMonth = 1;
        this.currentYear++;
      } else {
        this.currentMonth++;
      }
    },
    previous() {
      if(this.currentMonth === 1){
        this.currentMonth = 12;
        this.currentYear--;
      } else {
        this.currentMonth--;
      }
    },
    daysInMonth() {
      return new Date(this.currentYear, this.currentMonth, 0).getDate();
    },
    startDay() {
      return new Date(this.currentYear, this.currentMonth - 1, 1).getDay();
    },
    currentDate(num) {
      const calendarFullDate = new Date(this.currentYear, this.currentMonth -1, num).toDateString();
      const todayFullDate = new Date().toDateString();
      return calendarFullDate === todayFullDate;
    }
  },
  computed: {
    currentMonthName() {
      return new Date(this.currentYear, this.currentMonth -1).toLocaleString("default", { month: 'long' });
    },
  }
}
</script>

<style>

</style>