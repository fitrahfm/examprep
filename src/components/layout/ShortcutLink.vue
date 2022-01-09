<template>
  <card-wrapper title="Shortcuts" desc="For easy access">
    <template v-slot:body>
      <div class="colum q-mt-md q-mb-sm">
        <shortcut v-for="(data, index) in shortcuts" :key="index" :value="data" />
        <div class="q-mt-md">
          <divider />
        </div>
        <shortcut no-background :value="help" />
      </div>
    </template>
  </card-wrapper>
</template>

<script>
import { defineComponent } from 'vue';
import CardWrapper from 'components/ui/CardWrapper.vue';
import Shortcut from 'components/ui/Shortcut.vue';
import Divider from 'components/ui/Divider.vue';

export default defineComponent({
  name: 'ShortcutLink',
  components: {
    CardWrapper,
    Shortcut,
    Divider,
  },
  data() {
    return {
      shortcuts: [{
        caption: 'Focus on Weakness',
        icon: 'o_live_help',
        url: '/',
      }, {
        caption: 'Practice Exam',
        icon: 'o_alarm',
        url: '/',
      }, {
        caption: 'Task-Based Simulation',
        icon: 'o_ballot',
        url: '/',
      }, {
        caption: 'Reinforce Memory',
        icon: 'o_check_circle',
        url: '/',
      }],
      help: {
        caption: 'Help',
        icon: 'o_info',
        url: '/',
      },
    };
  },
});
</script>
