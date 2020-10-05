<template>
  <div class="about">
    <div
      class="cover"
      v-show="!isCalendarHidden"
    ></div>
    <div class="user-list-header">
      <div class="filter-buttons">
        <div
          class="filter-button"
          @click="() => isCalendarHidden = false"
        >
          <svg
            width="30"
            height="20"
            viewBox="0 0 30 20"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M21.5001 20H1C0.4 20 0 19.6 0 19V2.70001C0 2.10001
              0.4 1.70001 1 1.70001H21.5001C22.1001 1.70001 22.5001
              2.10001 22.5001 2.70001V19C22.5001 19.5 22.1001 20 21.5001
              20ZM2 18H20.5001V3.70001H2V18Z" fill="black"
            />
            <path d="M17.7002 5.29999C17.1002 5.29999 16.7002 4.89999
              16.7002 4.29999V1C16.7002 0.4 17.1002 0 17.7002 0C18.3002
              0 18.7002 0.4 18.7002 1V4.29999C18.7002 4.89999 18.3002
              5.29999 17.7002 5.29999Z" fill="black"
            />
            <path d="M5.00006 5.29999C4.40006 5.29999 4 4.89999 4
              4.29999V1C4 0.4 4.40006 0 5.00006 0C5.60006 0 6.00006
              0.4 6.00006 1V4.29999C6.00006 4.89999 5.50006 5.29999
              5.00006 5.29999Z" fill="black"
            />
            <path d="M21.5002 8.60004H1.2002C0.900195 8.60004 0.700195
              8.40004 0.700195 8.10004C0.700195 7.80004 0.900195 7.60004
              1.2002 7.60004H21.5002C21.8002 7.60004 22.0002 7.80004
              22.0002 8.10004C22.0002 8.30004 21.8002 8.60004 21.5002
              8.60004Z" fill="black"
            />
            <path d="M5.7002 10.6H3.7002V12.5H5.7002V10.6Z" fill="black"/>
            <path d="M9.00012 10.6H7.1001V12.5H9.00012V10.6Z" fill="black"/>
            <path d="M12.3999 10.6H10.5V12.5H12.3999V10.6Z" fill="black"/>
            <path d="M15.7998 10.6H13.7998V12.5H15.7998V10.6Z" fill="black"/>
            <path d="M19.1002 10.6H17.2002V12.5H19.1002V10.6Z" fill="black"/>
            <path d="M5.7002 13.7H3.7002V15.7H5.7002V13.7Z" fill="black"/>
            <path d="M9.00012 13.7H7.1001V15.7H9.00012V13.7Z" fill="black"/>
            <path d="M12.3999 13.7H10.5V15.7H12.3999V13.7Z" fill="black"/>
            <path d="M15.7998 13.7H13.7998V15.7H15.7998V13.7Z" fill="black"/>
            <path d="M19.1002 13.7H17.2002V15.7H19.1002V13.7Z" fill="black"/>
          </svg>
          <span class="button-text">За 1 день</span>
          <svg
            width="11"
            height="6"
            viewBox="0 0 11 6"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M5.5 6C5.21552 6 5.02591 5.91178 4.83625
              5.7353L0.284483 1.50002C-0.0948276 1.14708 -0.0948276
              0.617647 0.284483 0.264706C0.663793 -0.0882353 1.23278
              -0.0882353 1.61209 0.264706L5.5 3.88239L9.38791
              0.264706C9.76722 -0.0882353 10.3362 -0.0882353 10.7155
              0.264706C11.0948 0.617647 11.0948 1.14708 10.7155
              1.50002L6.16375 5.7353C5.97409 5.91178 5.68965 6 5.5 6Z"
              fill="black"
            />
          </svg>
        </div>
        <div class="filter-button">
          <svg
            width="25"
            height="24"
            viewBox="0 0 25 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M3.2998 10.5C2.6998 10.5 2.2998 10.1 2.2998
              9.5V1C2.2998 0.4 2.6998 0 3.2998 0C3.8998 0 4.2998
              0.4 4.2998 1V9.5C4.2998 10 3.7998 10.5 3.2998 10.5Z"
              fill="black"
            />
            <path d="M3.2998 23.5C2.6998 23.5 2.2998 23.1 2.2998
              22.5V15.2C2.2998 14.6 2.6998 14.2 3.2998 14.2C3.8998
              14.2 4.2998 14.6 4.2998 15.2V22.5C4.2998 23.1 3.7998
              23.5 3.2998 23.5Z" fill="black"
            />
            <path d="M3.29999 15.7999C1.49999 15.7999 0 14.3 0 12.5C0
              10.7 1.49999 9.19995 3.29999 9.19995C5.09999 9.19995
              6.60004 10.7 6.60004 12.5C6.60004 14.3 5.09999 15.7999
              3.29999 15.7999ZM3.29999 11.2999C2.59999 11.2999 2 11.9
              2 12.6C2 13.3 2.59999 13.8999 3.29999 13.8999C3.99999
              13.8999 4.60004 13.3 4.60004 12.6C4.60004 11.9 3.99999
              11.2999 3.29999 11.2999Z" fill="black"
            />
            <path d="M10.6997 15.2C10.0997 15.2 9.69971 14.8 9.69971
              14.2V1C9.69971 0.4 10.0997 0 10.6997 0C11.2997 0 11.6997
              0.4 11.6997 1V14.2C11.6997 14.7 11.2997 15.2 10.6997
              15.2Z" fill="black"
            />
            <path d="M10.6997 23.5C10.0997 23.5 9.69971 23.1 9.69971
              22.5V19.2C9.69971 18.6 10.0997 18.2 10.6997 18.2C11.2997
              18.2 11.6997 18.6 11.6997 19.2V22.5C11.6997 23.1 11.2997
              23.5 10.6997 23.5Z" fill="black"
            />
            <path d="M10.6999 19.7999C8.89989 19.7999 7.3999 18.3
              7.3999 16.5C7.3999 14.7 8.89989 13.2 10.6999 13.2C12.4999
              13.2 13.9999 14.7 13.9999 16.5C13.9999 18.3 12.4999
              19.7999 10.6999 19.7999ZM10.6999 15.2999C9.99989 15.2999
              9.3999 15.9 9.3999 16.6C9.3999 17.3 9.99989 17.8999
              10.6999 17.8999C11.3999 17.8999 11.9999 17.3 11.9999
              16.6C11.9999 15.9 11.3999 15.2999 10.6999 15.2999Z"
              fill="black"
            />
            <path d="M18.1997 5.69995C17.5997 5.69995 17.1997 5.29995
              17.1997 4.69995V1C17.1997 0.4 17.5997 0 18.1997 0C18.7997
              0 19.1997 0.4 19.1997 1V4.69995C19.1997 5.19995 18.7997
              5.69995 18.1997 5.69995Z" fill="black"
            />
            <path d="M18.1997 23.5C17.5997 23.5 17.1997 23.1 17.1997
              22.5V9.5C17.1997 8.9 17.5997 8.5 18.1997 8.5C18.7997 8.5
              19.1997 8.9 19.1997 9.5V22.5C19.1997 23.1 18.7997 23.5
              18.1997 23.5Z" fill="black"
            />
            <path d="M18.1999 10.2C16.3999 10.2 14.8999 8.6999 14.8999
              6.8999C14.8999 5.0999 16.3999 3.59998 18.1999
              3.59998C19.9999 3.59998 21.4999 5.0999 21.4999
              6.8999C21.4999 8.6999 19.9999 10.2 18.1999 10.2ZM18.1999
              5.69995C17.4999 5.69995 16.8999 6.3 16.8999 7C16.8999
              7.7 17.4999 8.29993 18.1999 8.29993C18.8999 8.29993
              19.4999 7.7 19.4999 7C19.4999 6.3 18.8999 5.69995
              18.1999 5.69995Z" fill="black"
            />
          </svg>
          <span class="button-text">Фильтр</span>
          <svg
            width="11"
            height="6"
            viewBox="0 0 11 6"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M5.5 6C5.21552 6 5.02591 5.91178 4.83625
              5.7353L0.284483 1.50002C-0.0948276 1.14708 -0.0948276
              0.617647 0.284483 0.264706C0.663793 -0.0882353 1.23278
              -0.0882353 1.61209 0.264706L5.5 3.88239L9.38791
              0.264706C9.76722 -0.0882353 10.3362 -0.0882353 10.7155
              0.264706C11.0948 0.617647 11.0948 1.14708 10.7155
              1.50002L6.16375 5.7353C5.97409 5.91178 5.68965 6 5.5 6Z"
              fill="black"
            />
          </svg>
        </div>
      </div>
      <div>
        <button class="button-black">Выгрузить</button>
        <button class=" button-orange">Добавить контакты</button>
      </div>
    </div>
    <div
      class="calendar"
      v-show="!isCalendarHidden"
    >
      <ul class="suggestions">
        <li
          :class="{rangeSelected: suggestionsSelected === 1}"
          @click="setSelectedDays('All')">Весь срок</li>
        <li
          :class="{rangeSelected: suggestionsSelected === 2}"
          @click="setSelectedDays('Today')">Сегодня</li>
        <li
          :class="{rangeSelected: suggestionsSelected === 3}"
          @click="setSelectedDays('Yesterday')">Вчера</li>
        <li
          :class="{rangeSelected: suggestionsSelected === 4}"
          @click="setSelectedDays('Last7')">Последние 7 дней</li>
        <li
          :class="{rangeSelected: suggestionsSelected === 5}"
          @click="setSelectedDays('Last30')">Последние 30 дней</li>
        <li
          :class="{rangeSelected: suggestionsSelected === 6}"
          @click="setSelectedDays('ThisMonth')">В этом месяце</li>
        <li
          :class="{rangeSelected: suggestionsSelected === 7}"
          @click="setSelectedDays('PrevMonth')">Прошлый месяц</li>
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
              class="calendar-numbers inactive"
              v-bind:class="{'selected': selectedDays.includes(new Date(
                currentDate.year,
                currentDate.month - 1,
                prevMonthDays() - firstDay() + n,
              ).getTime())}"
              v-for="(n, index) in firstDay()"
              :key="'prev' + index"
              @click="handleClick"
            >
              <div
                class="before"
                v-show="showBefore(new Date(
                currentDate.year,
                currentDate.month - 1,
                prevMonthDays() - firstDay() + n,
              ).getTime())"
              ></div>
              <div data-month="-1">{{prevMonthDays() - firstDay() + n}}</div>
              <div
                class="after"
                v-show="showAfter(new Date(
                currentDate.year,
                currentDate.month - 1,
                prevMonthDays() - firstDay() + n,
              ).getTime())"
              ></div>
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
              <div data-month="0">{{n}}</div>
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
              class="calendar-numbers inactive"
              v-bind:class="{'selected': selectedDays.includes(new Date(
                currentDate.year,
                currentDate.month + 1,
                n,
              ).getTime())}"
              v-for="(n, index) in (7 - (firstDayNextMonth() || 7))"
              :key="'next' + index"
              @click="handleClick"
            >
              <div
                class="before"
                v-show="showBefore(new Date(
                currentDate.year,
                currentDate.month + 1,
                n,
              ).getTime())"
              ></div>
              <div data-month="1">{{n}}</div>
              <div
                class="after"
                v-show="showAfter(new Date(
                currentDate.year,
                currentDate.month + 1,
                n,
              ).getTime())"
              ></div>
            </div>
          </div>
        </div>
        <button
          class="button-black"
          @click="handleCancel"
        >Отмена</button>
        <button
          class="button-orange"
          @click="() => isCalendarHidden = true"
        >Обновить</button>
      </div>
    </div>
    <div class="results-table">
      <div class="results-table-header">
        <input id="check" type="checkbox" hidden>
        <label for="check" class="checkbox"></label>
        <div>Пользователь</div>
        <div>Дата регистрации</div>
        <div>Последняя активность</div>
        <div>Последнее действие</div>
        <div>Продукт</div>
        <div><span>Отобразить 15</span> <img src="../assets/Arrow.svg" alt=""></div>
      </div>
      <div class="results-table-body">
        <div
          class="table-row"
          v-for="user in filterDatabase()"
          :key="user.id"
        >
          <input :id="user.id" type="checkbox" hidden>
          <label :for="user.id" class="checkbox"></label>
          <div>{{user.user}}<br>{{user.email}}</div>
          <div>{{user.regDate.toLocaleDateString()}}</div>
          <div>{{user.lastDate.toLocaleDateString()}}</div>
          <div>{{user.lastAction}}</div>
          <div>{{user.product}}</div>
          <img src="../assets/pensil.svg" alt="">
          <img src="../assets/trashcan.svg" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isCalendarHidden: true,
      database: [
        {
          id: 1,
          user: 'User1',
          email: 'user@user.com',
          selected: false,
          regDate: new Date(),
          lastDate: new Date(),
          lastAction: 'action',
          product: 'product',
        },
        {
          id: 2,
          user: 'User2',
          email: 'user@user.com',
          selected: false,
          regDate: new Date(),
          lastDate: new Date(),
          lastAction: 'action',
          product: 'product',
        },
        {
          id: 3,
          user: 'User3',
          email: 'user@user.com',
          selected: false,
          regDate: new Date(),
          lastDate: new Date(),
          lastAction: 'action',
          product: 'product',
        },
        {
          id: 4,
          user: 'User4',
          email: 'user@user.com',
          selected: false,
          regDate: new Date(),
          lastDate: new Date(),
          lastAction: 'action',
          product: 'product',
        },
        {
          id: 5,
          user: 'User5',
          email: 'user@user.com',
          selected: false,
          regDate: new Date(),
          lastDate: new Date(),
          lastAction: 'action',
          product: 'product',
        },
        {
          id: 6,
          user: 'User6',
          email: 'user@user.com',
          selected: false,
          regDate: new Date(),
          lastDate: new Date(),
          lastAction: 'action',
          product: 'product',
        },
      ],
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
      suggestionsSelected: 0,
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
      this.suggestionsSelected = 0;
      if (this.selectedDays.length === 2) {
        this.selectedDays = [];
      }
      if (!this.selectedDays.includes(new Date(
        this.currentDate.year,
        this.currentDate.month + +event.target.dataset.month,
        event.target.innerHTML,
      ).getTime())) {
        this.selectedDays.push(new Date(
          this.currentDate.year,
          this.currentDate.month + +event.target.dataset.month,
          event.target.innerHTML,
        ).getTime());
      }
    },
    handleCancel() {
      this.suggestionsSelected = 0;
      this.selectedDays = [];
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
        this.suggestionsSelected = 1;
        this.selectedDays = [-Infinity, Infinity];
      }
      if (range === 'Today') {
        this.suggestionsSelected = 2;
        this.getCurrentDate();
        this.selectedDays = [new Date(
          this.currentDate.year,
          this.currentDate.month,
          this.currentDate.date,
        ).getTime()];
      }
      if (range === 'Yesterday') {
        this.suggestionsSelected = 3;
        this.getCurrentDate();
        this.selectedDays = [new Date(
          this.currentDate.year,
          this.currentDate.month,
          this.currentDate.date - 1,
        ).getTime()];
      }
      if (range === 'Last7') {
        this.suggestionsSelected = 4;
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
        this.suggestionsSelected = 5;
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
        this.suggestionsSelected = 6;
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
        this.suggestionsSelected = 7;
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
    filterDatabase() {
      const x = this.database.filter((user) => (
        user.regDate.getTime() >= Math.min(...this.selectedDays)
        && user.regDate.getTime() < Math.max(...this.selectedDays) + 86400000));
      return x;
    },
  },
  created() {
    this.getCurrentDate();
  },
};
</script>

<style scoped>
.about {
  position: relative;
}

.cover {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(222, 184, 135, 0.479);
  z-index: 1;
  background: rgba(240, 246, 252, 0.7);
  backdrop-filter: blur(4px);
}

.user-list-header,
.results-table {
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

.filter-button:hover,
.filter-button:hover svg path {
  color: #FF7439;
  fill: #FF7439;
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
  outline: none;
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
  outline: none;
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

.rangeSelected {
  border: 2px solid #EBEEF3;
  background-color: #EBEEF3;
}

.calendar {
  position: absolute;
  top: 50px;
  display: flex;
  z-index: 2;
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
  height: 30px;
  line-height: 30px;
  justify-content: space-around;
}

.calendar-container {
  display: grid;
  position: relative;
  grid-template-columns: repeat(7, 41px);
  grid-auto-rows: 28px;
  grid-row-gap: 2px;
  justify-items: center;
  z-index: 2;
}

.calendar-numbers {
  position: relative;
  width: 28px;
  height: 28px;
  line-height: 28px;
  border-radius: 14px;
}

.before {
  position: absolute;
  left: -6px;
  display: block;
  height: 28px;
  width: 20px;
  background-color:#F5DED6;
  z-index: -1;
}

.after {
  position: absolute;
  top: 0;
  left: 14px;
  display: block;
  height: 28px;
  width: 21px;
  background-color: #F5DED6;
  z-index: -1;
}

.selected {
  background-color: orangered;
  position: relative;
}

.inactive:hover,
.calendar-numbers:hover {
  display: block;
  position: relative;
  width: 28px;
  height: 28px;
  border-radius: 14px;
  background-color: #aaa;
}

.inactive {
  color: #aaa;
}

.left {
  transform: rotate(180deg)
}

.checkbox {
  display: block;
  height: 16px;
  width: 16px;
  border-radius: 10px;
  border: 2px solid #DADDE2;
}

input:checked+.checkbox {
  background-color: #DADDE2;
}

.results-table {
  flex-direction: column;
  margin: 10px 0;
}

.results-table-body {
  width: 100%;
}

.results-table-header,
.table-row {
  display: flex;
  width: 100%;
  justify-content: space-between;
  height: 50px;
  align-items: center;
}
</style>
