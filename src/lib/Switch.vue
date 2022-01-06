<template>
  <div>
    <button @click="toggle" :class="{checked: value}">
      <span></span>
    </button>
  </div>
</template>

<script lang="ts">
import {ref} from 'vue';

export default {
  name: 'Switch',
  props: {
    value: Boolean,
  },
  setup(props, context) {
    const toggle = () => {
      props.value = !props.value;
      context.emit('update:value', !props.value)
    };
    return {
      toggle
    };
  }
};
</script>

<style lang="scss" scoped>

$h: 22px;

button {
  height: $h;
  width: $h *2;
  border: none;
  background-color: #bfbfbf;
  border-radius: $h / 2;
  position: relative;

  > span {
    position: absolute;
    height: $h;
    width: $h;
    background-color: white;
    border-radius: $h / 2;
    left: 2px;
    top: 0px;
    transition: left 250ms;
  }
}

.checked {
  background: #1890ff;

  span {
    left: calc(44px - #{$h} - 2px);
  }

}

</style>