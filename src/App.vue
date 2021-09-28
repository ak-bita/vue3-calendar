<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent(() => {
  return {
    hoge: 'ohohohohohoh',
  };
});
</script>

<template>
  <div :class="$style.wrap">
    <header :class="$style.header">
      <button type="button" :class="[$style.header__pagenationButton, $style.header__prevButton]">＜</button>
      <p :class="$style.header__currentYearAndMonth">2021 / 9</p>
      <button type="button" :class="[$style.header__pagenationButton, $style.header__nextButton]">＞</button>
    </header>
    <main>
      <div :class="$style.weekDayWrap">
        <p :class="$style.weekDayCell">日</p>
        <p :class="$style.weekDayCell">月</p>
        <p :class="$style.weekDayCell">火</p>
        <p :class="$style.weekDayCell">水</p>
        <p :class="$style.weekDayCell">木</p>
        <p :class="$style.weekDayCell">金</p>
        <p :class="$style.weekDayCell">土</p>
      </div>
      <div :class="$style.dayWrap">
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">29</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">30</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">31</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">1</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">2</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">3</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">4</p>
        </div>

        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">5</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">6</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">7</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">8</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">9</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">10</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">11</p>
        </div>

        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">12</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">13</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">14</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">15</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">16</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">17</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">18</p>
        </div>

        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">19</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">20</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">21</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">22</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">23</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">24</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">25</p>
        </div>

        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">26</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">27</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="[$style.dayCell__day, $style['dayCell__day--today']]">28</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">29</p>
        </div>
        <div :class="$style.dayCell">
          <p :class="$style.dayCell__day">30</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">1</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">2</p>
        </div>

        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">3</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">4</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">5</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">6</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">7</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">8</p>
        </div>
        <div :class="[$style.dayCell, $style['dayCell--otherMonth']]">
          <p :class="$style.dayCell__day">9</p>
        </div>
      </div>
    </main>
  </div>
</template>

<style lang="scss" module>
.wrap {
  font-size: 14px;
  color: #161616;
}

.header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px 0;
  background-color: #000;
}

.header__currentYearAndMonth {
  margin: 0 20px;
  font-size: 24px;
  color: #f3f3f3;
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
  border-color: #dadce0;
  border-style: solid;
  border-width: 0 1px 1px 0;
  padding: 2px 0;
  width: calc((100vw - 1px) / 7);
  text-align: center;
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
  width: calc((100vw - 1px) / 7);
  padding: 10px;
}

.dayCell--otherMonth {
  background-color: #fffaef;
}

.dayCell__day {
  text-align: center;
  width: 24px;
  height: 24px;
  line-height: 24px;
}

.dayCell__day--today {
  background-color: #da292a;
  border-radius: 50%;
  color: #fff;
}
</style>
