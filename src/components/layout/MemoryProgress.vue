<template>
  <card-wrapper no-divider title="Memory Progress" desc="Your learning progress">
    <template v-slot:body>
      <div class="row justify-between">
        <mastery-stats :value="conceptData" />
        <current-course />
      </div>
    </template>
  </card-wrapper>
</template>

<script>
import { defineComponent } from 'vue';
import CardWrapper from 'components/ui/CardWrapper.vue';
import MasteryStats from 'components/mastery/MasteryStats.vue';
import CurrentCourse from 'components/learn/CurrentCourse.vue';

export default defineComponent({
  name: 'MemoryProgress',
  components: {
    CardWrapper,
    MasteryStats,
    CurrentCourse,
  },
  data() {
    return {
      conceptData: {
        mastered: 7,
        total: 15,
      },
    };
  },
});
</script>
