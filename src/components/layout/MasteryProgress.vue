<template>
  <card-wrapper no-divider tooltips title="Mastery Ranges"
    desc="Take quiz to see mastery ranges"
    class="q-pa-md"
  >
    <template v-slot:body>
      <mastery-range v-for="(data, index) in value" :key="index" :value="data" />
    </template>
  </card-wrapper>
</template>

<script>
import { defineComponent } from 'vue';
import CardWrapper from 'components/ui/CardWrapper.vue';
import MasteryRange from 'components/mastery/MasteryRange.vue';

export default defineComponent({
  name: 'MasteryProgress',
  components: {
    CardWrapper,
    MasteryRange,
  },
  data() {
    return {
      value: [{
        title: 'Conceptual Framework, Standard-Setting and Financial Reporting',
        uri: '',
        data: {
          weight: '30%',
          min: 36,
          max: 65,
          current: 45,
        },
      }, {
        title: 'Select Financial Statement Accounts',
        uri: '',
        data: {
          weight: '35%',
          min: 1,
          max: 35,
          current: 14,
        },
      }, {
        title: 'Select Transactions',
        uri: '',
        data: {
          weight: '25%',
          min: 65,
          max: 90,
        },
      }, {
        title: 'State and Local Governments',
        uri: '',
        data: {
          weight: '10%',
          min: 90,
          max: 100,
        },
      }],
    };
  },
});
</script>
