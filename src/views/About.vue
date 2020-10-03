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
        <li @click="setSelectedDays('All')">Весь срок</li>
        <li @click="setSelectedDays('Today')">Сегодня</li>
        <li @click="setSelectedDays('Yesterday')">Вчера</li>
        <li @click="setSelectedDays('Last7')">Последние 7 дней</li>
        <li @click="setSelectedDays('Last30')">Последние 30 дней</li>
        <li @click="setSelectedDays('ThisMonth')">В этом месяце</li>
        <li @click="setSelectedDays('PrevMonth')">Прошлый месяц</li>
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
              v-bind:class="{'selected': selectedDays.includes(new Date(
                currentDate.year,
                currentDate.month,
                n,
              ).getTime())}"
              v-for="(n, index) in lastDate()"
              :key="'current' + index"
              @click="handleClick"
            >
              <div
                class="before"
                v-show="showBefore(new Date(
                currentDate.year,
                currentDate.month,
                n,
              ).getTime())"
              ></div>
              <div>{{n}}</div>
              <div
                class="after"
                v-show="showAfter(new Date(
                currentDate.year,
                currentDate.month,
                n,
              ).getTime())"
              ></div>
            </div>
            <div
              class="calendar-prevNumbers"
              v-for="(n, index) in (7 - (firstDayNextMonth() || 7))"
              :key="'next' + index"
            >
              {{n}}
            </div>
          </div>
        </div>
        <button class="button-black">Отмена</button>
        <button class="button-orange">Обновить</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      weekdays: ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс'],
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
      selectedDays: [],
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
      } else {
        this.currentDate.month -= 1;
      }
    },
    nextMonth() {
      if (this.currentDate.month === 11) {
        this.currentDate.month = 0;
        this.currentDate.year += 1;
      } else {
        this.currentDate.month += 1;
      }
    },
    prevMonthDays() {
      const year = this.currentDate.month === 0
        ? this.currentDate.year - 1
        : this.currentDate.year;
      const month = this.currentDate.month === 0 ? 12 : this.currentDate.month;
      return new Date(year, month, 0).getDate();
    },
    nextMonthDays() {
      const year = this.currentDate.month === 11
        ? this.currentDate.year + 1
        : this.currentDate.year;
      const month = this.currentDate.month === 11 ? 0 : this.currentDate.month;
      return new Date(year, month, 0).getDate();
    },
    firstDay() {
      return new Date(
        this.currentDate.year,
        this.currentDate.month,
        0,
      ).getDay();
    },
    firstDayNextMonth() {
      return new Date(
        this.currentDate.year,
        this.currentDate.month + 1,
        0,
      ).getDay();
    },
    lastDate() {
      return new Date(
        this.currentDate.year,
        this.currentDate.month + 1,
        0,
      ).getDate();
    },
    handleClick(event) {
      if (this.selectedDays.length === 2) {
        this.selectedDays = [];
      }
      if (!this.selectedDays.includes(new Date(
        this.currentDate.year,
        this.currentDate.month,
        event.target.innerHTML,
      ).getTime())) {
        this.selectedDays.push(new Date(
          this.currentDate.year,
          this.currentDate.month,
          event.target.innerHTML,
        ).getTime());
      }
      console.log(this.selectedDays);
    },
    showBefore(n) {
      if (this.selectedDays.length < 2) {
        return false;
      }
      if (n > Math.min(...this.selectedDays)
        && n <= Math.max(...this.selectedDays)) {
        return true;
      }
      return false;
    },
    showAfter(n) {
      if (this.selectedDays.length < 2) {
        return false;
      }
      if (n >= Math.min(...this.selectedDays)
        && n < Math.max(...this.selectedDays)) {
        return true;
      }
      return false;
    },
    setSelectedDays(range) {
      if (range === 'All') {
        this.selectedDays = [-Infinity, Infinity];
      }
      if (range === 'Today') {
        this.getCurrentDate();
        this.selectedDays = [new Date(
          this.currentDate.year,
          this.currentDate.month,
          this.currentDate.date,
        ).getTime()];
      }
      if (range === 'Yesterday') {
        this.getCurrentDate();
        this.selectedDays = [new Date(
          this.currentDate.year,
          this.currentDate.month,
          this.currentDate.date - 1,
        ).getTime()];
      }
      if (range === 'Last7') {
        this.getCurrentDate();
        this.selectedDays = [
          new Date(
            this.currentDate.year,
            this.currentDate.month,
            this.currentDate.date - 6,
          ).getTime(),
          new Date(
            this.currentDate.year,
            this.currentDate.month,
            this.currentDate.date,
          ).getTime(),
        ];
      }
      if (range === 'Last30') {
        this.getCurrentDate();
        this.selectedDays = [
          new Date(
            this.currentDate.year,
            this.currentDate.month,
            this.currentDate.date - 29,
          ).getTime(),
          new Date(
            this.currentDate.year,
            this.currentDate.month,
            this.currentDate.date,
          ).getTime(),
        ];
      }
      if (range === 'ThisMonth') {
        this.getCurrentDate();
        this.selectedDays = [
          new Date(
            this.currentDate.year,
            this.currentDate.month,
            1,
          ).getTime(),
          new Date(
            this.currentDate.year,
            this.currentDate.month,
            this.currentDate.date,
          ).getTime(),
        ];
      }
      if (range === 'PrevMonth') {
        this.getCurrentDate();
        this.selectedDays = [
          new Date(
            this.currentDate.year,
            this.currentDate.month -= 1,
            1,
          ).getTime(),
          new Date(
            this.currentDate.year,
            this.currentDate.month += 1,
            0,
          ).getTime(),
        ];
        this.currentDate.month -= 1;
      }
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

.calendar-numbers {
  position: relative;
  width: 20px;
  height: 20px;
  border-radius: 10px;
  transform: translateX(50%);
}

.before {
  position: absolute;
  left: -10px;
  display: block;
  height: 20px;
  width: 20px;
  background-color:rgba(255, 116, 57, 0.2);
  z-index: -1;
}

.after {
  position: absolute;
  top: 0;
  left: 10px;
  display: block;
  height: 20px;
  width: 20px;
  background-color: rgba(255, 116, 57, 0.2);
  z-index: -2;
}

.selected {
  background-color: orangered;
}

.calendar-prevNumbers:hover,
.calendar-numbers:hover {
  display: block;
  width: 20px;
  height: 20px;
  border-radius: 10px;
  background-color: #aaa;
}

.calendar-prevNumbers {
  color: #aaa;
}

.left {
  transform: rotate(180deg)
}
</style>
