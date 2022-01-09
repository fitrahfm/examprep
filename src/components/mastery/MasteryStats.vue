<template>
  <card-wrapper no-header color="grey-2" size="40" class="q-my-md">
    <template v-slot:body-top>
      <span>Concepts Mastered</span>
    </template>
    <template v-slot:body>
      <div class="column justify-center items-center" style="height: 135px">
        <q-circular-progress
          show-value
          :value="progressValue"
          size="100px"
          :thickness="0.15"
          color="blue-6"
          track-color="grey-4"
          class="q-mt-lg q-mb-xs"
        >
          <div class="progress__value column justify-center items-center"
            style="font-size: 20px;"
            >
            <div class="row text-blue-6">
              <span>
                {{ progressValue }}
              </span>
              <span style="font-size: 16px">%</span>
            </div>
            <span class="text-grey-8" style="font-size: 12px;">
              {{ value.mastered }} / {{ value.total }}
            </span>
          </div>
        </q-circular-progress>
      </div>
    </template>
    <template v-slot:body-bottom>
      <div class="row justify-end q-mt-lg">
        <q-btn flat dense no-caps color="blue-8" @click="dialogStatus = true">
          <span>Concepts</span>
          <q-icon size="10px" name="o_arrow_forward" />
        </q-btn>
      </div>
      <concept-mastery-modal :isOpen="dialogStatus" @close="dialogStatus = !dialogStatus" />
    </template>
  </card-wrapper>
</template>

<script>
import { defineComponent } from 'vue';
import CardWrapper from 'components/ui/CardWrapper.vue';
import ConceptMasteryModal from 'components/mastery/ConceptMasteryModal.vue';

export default defineComponent({
  name: 'ConceptMastering',
  components: {
    CardWrapper,
    ConceptMasteryModal,
  },
  props: {
    value: Object,
  },
  data() {
    return {
      dialogStatus: false,
    };
  },
  computed: {
    progressValue() {
      const value = (this.value.mastered / this.value.total) * 100;
      return value.toFixed(1);
    },
  },
});
</script>
