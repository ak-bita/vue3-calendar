<script lang="ts">
import { defineComponent, ref, computed } from 'vue';
import moment from 'moment';

export default defineComponent({
  setup() {
    const cellCount = 42 as const;
    const week = ['日', '月', '火', '水', '木', '金', '土'] as const;
    const todayDate = ref(moment());

    const addMonth = () => {
      todayDate.value = moment(todayDate.value).add(1, 'month');
    };

    const removeMonth = () => {
      todayDate.value = moment(todayDate.value).subtract(1, 'month');
    };

    const displayDates = computed(() => {
      return [...Array(cellCount)].map((_, index) => {
        const firstDatMonth = moment(todayDate.value).startOf('month');
        // target = 1番目に表示する日にちを取得する（前の月を跨ぐ）
        const target = firstDatMonth.subtract(firstDatMonth.day(), 'day');
        // newTarget = 1番目に表示する日にちから index日分プラスした日にちを取得する
        const newTarget = target.add(index, 'day');
        const isThisMonth = moment(newTarget).format('YYYYMM') === moment(todayDate.value).format('YYYYMM');
        const isToday = moment(newTarget).format('YYYYMMDD') === moment().format('YYYYMMDD');
        return { month: newTarget.month() + 1, day: newTarget.date(), isThisMonth, isToday };
      });
    });

    return {
      week,
      todayDate,
      displayDates,
      addMonth,
      removeMonth,
    };
  },
});
</script>

<template>
  <div :class="$style.wrap">
    <header :class="$style.header">
      <button type="button" :class="[$style.header__pagenationButton, $style.header__prevButton]" @click="removeMonth">
        ＜
      </button>
      <p :class="$style.header__currentYearAndMonth">{{ todayDate.year() }} / {{ todayDate.month() + 1 }}</p>
      <button type="button" :class="[$style.header__pagenationButton, $style.header__nextButton]" @click="addMonth">
        ＞
      </button>
    </header>
    <main>
      <div :class="$style.weekDayWrap">
        <p v-for="weekItem in week" :key="weekItem" :class="$style.weekDayCell">{{ weekItem }}</p>
      </div>
      <div :class="$style.dayWrap">
        <div
          v-for="date in displayDates"
          :key="date"
          :class="[$style.dayCell, !date.isThisMonth && $style['dayCell--otherMonth']]"
        >
          <p :class="[$style.dayCell__day, date.isToday && $style['dayCell__day--today']]">{{ date.day }}</p>
        </div>
      </div>
    </main>
  </div>
</template>

<style lang="scss" module>
.wrap {
  color: #161616;
  font-size: 14px;
}

.header {
  align-items: center;
  background-color: #000;
  display: flex;
  justify-content: center;
  padding: 20px 0;
}

.header__currentYearAndMonth {
  color: #f3f3f3;
  font-size: 24px;
  margin: 0 20px;
}

.header__pagenationButton {
  color: #f3f3f3;
}

.weekDayWrap {
  border-color: #dadce0;
  border-style: solid;
  border-width: 1px 0 0 1px;
  display: flex;
}

.weekDayCell {
  background-color: #585858;
  border-color: #dadce0;
  border-style: solid;
  border-width: 0 1px 1px 0;
  color: #fff;
  padding: 2px 0;
  text-align: center;
  width: calc((100vw - 1px) / 7);
}

.dayWrap {
  border-color: #dadce0;
  border-style: solid;
  border-width: 0 0 0 1px;
  display: flex;
  flex-wrap: wrap;
  height: calc(100vh - 64px - 20px);
}

.dayCell {
  border-color: #dadce0;
  border-style: solid;
  border-width: 0 1px 1px 0;
  padding: 10px;
  width: calc((100vw - 1px) / 7);
}

.dayCell--otherMonth {
  background-color: #fffaef;
}

.dayCell__day {
  height: 24px;
  line-height: 24px;
  text-align: center;
  width: 24px;
}

.dayCell__day--today {
  background-color: #da292a;
  border-radius: 50%;
  color: #fff;
}
</style>
