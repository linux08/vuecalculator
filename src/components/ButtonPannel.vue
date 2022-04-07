<template>
    <div class="component-button-panel">
        <div>
          <Button name="AC" :handleClick="handleClick" />
          <Button name="+/-" :handleClick="handleClick" />
          <Button name="%" :handleClick="handleClick" />
          <Button name="÷" :handleClick="handleClick" isOrange />
        </div>
        <div>
          <Button name="7" :handleClick="handleClick" />
          <Button name="8" :handleClick="handleClick" />
          <Button name="9" :handleClick="handleClick" />
          <Button name="x" :handleClick="handleClick" isOrange />
        </div>
        <div>
          <Button name="4" :handleClick="handleClick" />
          <Button name="5" :handleClick="handleClick" />
          <Button name="6" :handleClick="handleClick" />
          <Button name="-" :handleClick="handleClick" isOrange />
        </div>
        <div>
          <Button name="1" :handleClick="handleClick" />
          <Button name="2" :handleClick="handleClick" />
          <Button name="3" :handleClick="handleClick" />
          <Button name="+" :handleClick="handleClick" isOrange />
        </div>
        <div>
          <Button name="0" :handleClick="handleClick" isWide />
          <Button name="." :handleClick="handleClick" />
          <Button name="=" :handleClick="handleClick" isOrange />
        </div>
      </div>
</template>

<script setup>

import { defineProps } from 'vue';
import Button from './Button.vue';

const props = defineProps({
  clickHandler: Function,
});

const handleClick = (buttonName) => {
  props.clickHandler(buttonName);
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.component-button-panel {
  background-color: #858694;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  flex: 1 0 auto;
}

.component-button-panel > div {
  width: 100%;
  margin-bottom: 1px;
  flex: 1 0 auto;
  display: flex;
}

</style>
