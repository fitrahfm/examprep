<template>
  <q-page class="row justify-center align-top no-wrap">
    <div class="cards__left w-45 q-mr-sm">
      <learning-progress />
      <shortcut-link />
    </div>
    <div class="cards__right w-55 q-ml-sm">
      <memory-progress />
      <mastery-progress />
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import LearningProgress from 'components/layout/LearningProgress.vue';
import ShortcutLink from 'components/layout/ShortcutLink.vue';
import MemoryProgress from 'components/layout/MemoryProgress.vue';
import MasteryProgress from 'src/components/layout/MasteryProgress.vue';

export default defineComponent({
  name: 'Dashboard',
  components: {
    LearningProgress,
    ShortcutLink,
    MemoryProgress,
    MasteryProgress,
  },
});
</script>
