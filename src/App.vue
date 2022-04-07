<template>
  <div class="component-app">
    <Display
      :value="state.next || state.total || 0 "
     />
    <ButtonPanel :clickHandler="handleClick" />
  </div>
</template>

<script setup>
import { reactive } from 'vue';
import Display from './components/Display.vue';
import ButtonPanel from './components/ButtonPannel.vue';
import calculate from './logic/calculate';

const state = reactive({
  total: 0,
  next: null,
  operation: null,
});

const handleClick = (event) => {
  const { total, next, operation } = calculate(state, event);
  state.total = total;
  state.next = next;
  state.operation = operation;
};

</script>

<style>
.component-app {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  height: 100%;
}
</style>
