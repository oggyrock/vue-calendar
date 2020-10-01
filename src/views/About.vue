<template>
  <div class="about">
    <div class="user-list-header">
      <div class="filter-buttons">
        <div class="filter-button">
          <img src="@/assets/Calendar.svg" alt="Calendar icon">
          <span class="button-text">За 1 день</span>
          <img src="@/assets/Arrow.svg" alt="arrow icon">
        </div>
        <div class="filter-button">
          <img src="@/assets/Filter.svg" alt="Filter icon">
          <span class="button-text">Фильтр</span>
          <img src="@/assets/Arrow.svg" alt="arrow icon">
        </div>
      </div>
      <div>
        <button class="button-black">Выгрузить</button>
        <button class=" button-orange">Добавить контакты</button>
      </div>
    </div>
    <div class="calendar">
      <ul class="suggestions">
        <li>Весь срок</li>
        <li>Сегодня</li>
        <li>Вчера</li>
        <li>Последние 7 дней</li>
        <li>Последние 30 дней</li>
        <li>В этом месяце</li>
        <li>Прошлый месяц</li>
      </ul>
      <div class="calendar-field">
        <div class="calendar-header">
          <img
            class="left"
            src="@/assets/ArrowSide.svg"
            alt="arrow left icon"
            @click="prevMonth()"
          >
          <span>{{month[currentDate.month]}} {{currentDate.year}}</span>
          <img
            src="@/assets/ArrowSide.svg"
            alt="arrow right icon"
            @click="nextMonth()"

          >
        </div>
        <div class="calendar-body">
          <div class="calendar-first-row">
            <span
              v-for="(day, index) in weekdays"
              :key="index"
            >
              {{day}}
            </span>

          </div>
          <div class="calendar-container">
            <div
              class="calendar-prevNumbers"
              v-for="(n, index) in firstDay()"
              :key="'prev' + index"
            >
              {{prevMonthDays() - firstDay() + n}}
            </div>
            <div
              class="calendar-numbers"
              v-for="(n, index) in currentDate.date"
              :key="'current' + index"
            >
              {{n}}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      weekdays: ['Пн', 'Вт', 'Ср', 'Чт', 'Пн', 'Сб', 'Вс'],
      month: [
        'Январь',
        'Февраль',
        'Март',
        'Апрель',
        'Май',
        'Июнь',
        'Июль',
        'Август',
        'Сентябрь',
        'Октябрь',
        'Ноябрь',
        'Декабрь',
      ],
      currentDate: {
        date: 0,
        month: 0,
        year: 0,
      },
    };
  },
  methods: {
    getCurrentDate() {
      const today = new Date();
      this.currentDate.date = today.getDate();
      this.currentDate.month = today.getMonth();
      this.currentDate.year = today.getFullYear();
    },
    prevMonth() {
      if (this.currentDate.month === 0) {
        this.currentDate.month = 11;
        this.currentDate.year -= 1;
        this.currentDate.date = new Date(
          this.currentDate.year - 1,
          11,
          0,
        ).getDate();
      } else {
        this.currentDate.month -= 1;
        this.currentDate.date = new Date(
          this.currentDate.year,
          this.currentDate.month - 1,
          0,
        ).getDate();
      }
    },
    nextMonth() {
      if (this.currentDate.month === 11) {
        this.currentDate.month = 0;
        this.currentDate.year += 1;
        this.currentDate.date = new Date(
          this.currentDate.year + 1,
          0,
          0,
        ).getDate();
      } else {
        this.currentDate.month += 1;
        this.currentDate.date = new Date(
          this.currentDate.year,
          this.currentDate.month + 1,
          0,
        ).getDate();
      }
    },
    prevMonthDays() {
      const year = this.currentDate.month === 0 ? this.currentDate.year - 1 : this.currentDate.year;
      const month = this.currentDate.month === 0 ? 12 : this.currentDate.month;
      return new Date(year, month, 0).getDate();
    },
    firstDay() {
      return new Date(
        this.currentDate.year,
        this.currentDate.month,
        0,
      ).getDay();
    },
  },
  created() {
    this.getCurrentDate();
  },
};
</script>

<style scoped>
.user-list-header {
  display: flex;
  padding: 0 10px;
  border-radius: 10px;
  background-color: white;
  justify-content: space-between;
  align-items: center;
}

.filter-buttons {
  display: flex;
}

.filter-button {
  display: flex;
  align-items: center;
  padding: 10px;
}

.filter-button:hover {
  color: orangered;
}

.button-text {
  padding: 10px;
}

.button-black {
  height: 45px;
  box-sizing: border-box;
  background-color: white;
  border: 2px solid black;
  border-radius: 7px;
  margin: 20px 5px;
  padding: 0 20px;
}

.button-black:hover {
  background-color: black;
  color: white;
}

.button-orange {
  height: 45px;
  box-sizing: border-box;
  background-color: #FF7439;
  border: 2px solid #FF7439;
  border-radius: 7px;
  margin: 20px 5px;
  padding: 0 20px;
}

.button-orange:hover {
  background-color: #F16E36;
  border-color: #F16E36;
}

.suggestions {
  box-sizing: border-box;
  background-color: white;
  width: 176px;
  height: 332px;
  border-radius: 10px;
  list-style: none;
  padding: 10px;
  text-align: left;
}

.suggestions li {
  height: 39px;
  line-height: 39px;
  padding: 0 10px;
  box-sizing: border-box;
  border: 2px solid white;
  border-radius: 5px;
}

.suggestions li:hover {
  border: 2px solid #EBEEF3;
}

.calendar {
  display: flex;
}

.calendar-field {
  width: 288px;
  height: 332px;
  background-color: white;
  margin: 15px 10px;
  border-radius: 10px;
}

.calendar-header {
  display: flex;
  padding: 15px 0;
  overflow: hidden;
  justify-content: space-around;
  align-items: center;
}

.calendar-body {
  background-color: #F3F8FD;
}
.calendar-first-row {
  display: flex;
  justify-content: space-around;
}

.calendar-container {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
}

.calendar-prevNumbers {
  color: #aaa;
}

.left {
  transform: rotate(180deg)
}
</style>
