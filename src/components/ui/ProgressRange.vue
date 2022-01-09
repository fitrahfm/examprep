<template>
  <q-slider readonly v-model="sliderValue" :min="0" :max="100"
    :inner-min="value.min"
    :inner-max="value.max"
    thumb-size="24px"
    label
    label-always
  >
      <div
        class="marker__label"
      >
        <span>{{ value.current }}</span>
      </div>
  </q-slider>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ProgressRange',
  props: {
    value: Object,
  },
  computed: {
    sliderValue() {
      return this.value.current;
    },
  },
});
</script>
