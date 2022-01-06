<template>
  <div>
    <Switch v-model:value="bool"></Switch>
  </div>
</template>


<script>
import Switch from '../lib/Switch.vue';
import {ref, onUpdated} from 'vue';

export default {
  components: {Switch},

  setup() {
    const bool = ref(false);
    console.log(bool.value);

    onUpdated(() => {
      console.log(bool.value)
    });
    return {
      bool
    };
  }
};
</script>