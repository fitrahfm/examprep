<template>
  <q-dialog v-model="show">
    <card-wrapper title="Concept Mastery" desc="Hover over concepts for details"
      style="width: 1000px; max-width: 1000px;">
      <template v-slot:header>
        <div class="col-1 row justify-end items-start">
          <q-btn icon="close" flat round dense size="10px" @click="$emit('close')" />
        </div>
      </template>
      <template v-slot:body>
        <div class="row justify-between items-start no-wrap">
          <div class="w-75">
            <concept-mastery v-for="(value, index) in masteryData"
              :key="index"
              :value="value"
            />
          </div>
          <card-wrapper no-header class="mastery__keys w-25 radius-sm q-my-lg q-pa-md q-ml-md">
            <template v-slot:body>
              <div class="keys__title q-mb-sm">
                <span class="text-grey-8">Concept Mastery Keys</span>
              </div>
              <div class="keys_list column">
                <span class="text-grey-8">First Key</span>
                <span class="text-grey-8">Second Key</span>
                <span class="text-grey-8">Third Key</span>
                <span class="text-grey-8">Fourth Key</span>
              </div>
            </template>
          </card-wrapper>
        </div>
      </template>
    </card-wrapper>
  </q-dialog>
</template>

<script>
import { defineComponent } from 'vue';
import CardWrapper from 'components/ui/CardWrapper.vue';
import ConceptMastery from 'components/mastery/ConceptMastery.vue';

export default defineComponent({
  name: 'ConceptMasteryModal',
  components: {
    CardWrapper,
    ConceptMastery,
  },
  props: {
    isOpen: Boolean,
  },
  data() {
    return {
      masteryData: [{
        conceptTitle: 'Conceptual Framework, Standard-Setting and Financial Reporting',
        subs: [{
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: true,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: true,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: true,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: true,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: true,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: true,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          estimate: 0.3,
          active: true,
        }],
      }, {
        conceptTitle: 'Select Financial Statement Accounts',
        subs: [{
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: true,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }],
      }, {
        conceptTitle: 'Select Transitions',
        subs: [{
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }],
      }, {
        conceptTitle: 'State and Local Governments',
        subs: [{
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }, {
          title: 'Non-for-profit: statement of activities',
          caption: "You've shown a basic understanding, but probably have more to learn.",
          active: false,
        }],
      }],
    };
  },
  computed: {
    show() {
      return this.isOpen;
    },
  },
});
</script>
