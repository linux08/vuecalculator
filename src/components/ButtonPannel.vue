<template>
    <div class="component-button-panel">
        <div>
          <Button name="AC" @click="handleClick" />
          <Button name="+/-" @click="handleClick" />
          <Button name="%" @click="handleClick" />
          <Button name="÷" @click="handleClick" isOrange />
        </div>
        <div>
          <Button name="7" @click="handleClick" />
          <Button name="8" @click="handleClick" />
          <Button name="9" @click="handleClick" />
          <Button name="x" @click="handleClick" isOrange />
        </div>
        <div>
          <Button name="4" @click="handleClick" />
          <Button name="5" @click="handleClick" />
          <Button name="6" @click="handleClick" />
          <Button name="-" @click="handleClick" isOrange />
        </div>
        <div>
          <Button name="1" @click="handleClick" />
          <Button name="2" @click="handleClick" />
          <Button name="3" @click="handleClick" />
          <Button name="+" @click="handleClick" isOrange />
        </div>
        <div>
          <Button name="0" @click="handleClick" isWide />
          <Button name="." @click="handleClick" />
          <Button name="=" @click="handleClick" isOrange />
        </div>
      </div>
</template>

<script>

import Button from './Button.vue';

export default {
  components: { Button },
  name: 'ButtonPannel',
  props: {
    clickHandler: Function,
  },

  methods: {
    handleClick(buttonName) {
      console.log(buttonName);
      this.props.clickHandler(buttonName);
    },
  },
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
