<template>
  <div class="component-app">
    <Display
      :value="next || total || 0 "
     />
    <ButtonPanel :clickHandler="handleClick" />
  </div>
</template>

<script>
import Display from './components/Display.vue';
import ButtonPanel from './components/ButtonPannel.vue';
import calculate from './logic/calculate';

export default {
  components: { Display, ButtonPanel },
  name: 'App',
  data() {
    return {
      total: 0,
      next: null,
      operation: null,
    };
  },
  methods: {
    handleClick(event) {
      const { total, next, operation } = calculate(this.$data, event);
      this.total = total;
      this.next = next;
      this.operation = operation;
    },
  },
  computed: {
    displayValue() {
      return this.next || this.total || '0';
    },
  },
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
