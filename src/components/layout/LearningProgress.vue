<template>
  <card-wrapper title="My ReadyRating" desc="Readiness to pass the exam" tooltips>
    <template v-slot:body>
      <!-- Progress Step Component -->
      <progress-step :current="current">
        <template v-slot:header>
          <div class="ps__title row justify-center">
            <h6 class="text-blue-6">Keep studying...</h6>
          </div>
        </template>
        <template v-slot:caption>
          <div class="ps__caption q-my-sm">
            <span class="text-grey-7">
              Focus on practice questions emphasizing gaps from your study guide.
            </span>
          </div>
        </template>
        <template v-slot:body>
          <div class="row justify-center q-my-md">
            <q-btn outline color="blue-6" label="Submit Your Score" />
          </div>
        </template>
      </progress-step>
      <divider />
      <!-- Task List Component -->
      <div class="tasks q-mb-md">
        <progress-bar className="task__progress --questions" title="Adaptive Questions:"
          scores="55"
          max="55"
          cta="practice"
        />
        <progress-bar className="task__progress --simulations" title="Task-Based Sims:"
          scores="15"
          max="15"
          cta="practice"
        />
        <progress-bar no-divider className="task__progress --practices" title="Practice Exams:"
          scores="4"
          max="4"
          cta="practice"
        />
      </div>
    </template>
  </card-wrapper>
</template>

<script>
import { defineComponent } from 'vue';
import CardWrapper from 'components/ui/CardWrapper.vue';
import Divider from 'components/ui/Divider.vue';
import ProgressBar from 'components/ui/ProgressBar.vue';
import ProgressStep from 'components/ui/ProgressStep.vue';

export default defineComponent({
  name: 'LearningProgress',
  components: {
    CardWrapper,
    Divider,
    ProgressBar,
    ProgressStep,
  },
  data() {
    return {
      current: 1,
    };
  },
});
</script>
