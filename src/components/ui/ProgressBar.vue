<template>
  <div class="q-my-sm" :class="className">
    <div class="pt__header row q-mb-xs">
      <div class="col-9 row">
        <div class="pt__title">
          <span>{{ title }}&emsp;</span>
        </div>
        <div v-show="scores" class="pt__scores">
          <span>{{ scores }}</span>
        </div>
      </div>
      <div v-show="cta" class="pt__cta col-3 row justify-end">
        <q-btn flat dense size="sm" color="blue-6" :label="cta" />
      </div>
    </div>
    <q-linear-progress rounded class="q-mb-md"
      color="blue-6"
      size="md"
      :value="progressValue"
    />
    <divider v-show="!noDivider" />
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import Divider from 'components/ui/Divider.vue';

export default defineComponent({
  name: 'ProgressBar',
  components: {
    Divider,
  },
  props: {
    className: String,
    title: String,
    scores: Number,
    max: Number,
    cta: String,
    noDivider: Boolean,
  },
  computed: {
    progressValue() {
      const result = this.scores / this.max;
      return result;
    },
  },
});
</script>
