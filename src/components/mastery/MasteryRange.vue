<template>
  <card-wrapper no-header color="grey-2" class="q-my-md" style="padding-bottom: 0;">
    <template v-slot:body>
      <div class="column no-wrap">
        <div class="row justify-between items-center">
          <div class="mastery__title w-80">
            <span>{{ value.title }}</span>
          </div>
          <div class="mastery__quiz">
            <q-btn flat dense label="Take quiz" size="sm" color="blue-8" />
          </div>
        </div>
        <div class="mastery__weight">
          <span class="text-grey-8">Weight: {{ value.data.weight }}</span>
        </div>
        <div class="mastery__range">
          <progress-range :value="value.data" />
        </div>
      </div>
    </template>
  </card-wrapper>
</template>

<script>
import { defineComponent } from 'vue';
import CardWrapper from 'components/ui/CardWrapper.vue';
import ProgressRange from 'components/ui/ProgressRange.vue';

export default defineComponent({
  name: 'MasteryRange',
  components: {
    CardWrapper,
    ProgressRange,
  },
  props: {
    value: Object,
  },
});
</script>
