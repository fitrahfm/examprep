<template>
  <a class="shortcut__link row q-my-sm q-py-xs" :class="!noBackground ? 'bg-grey-3' : ''"
    :href="value.url"
  >
    <div class="sl__icon row justify-center items-center w-10">
      <q-icon :name="value.icon" size="xs" class="text-grey-8" />
    </div>
    <div class="sl__caption q-px-sm">
      <span :class="!noBackground ? 'text-grey-8' : ''">
        {{ value.caption }}
      </span>
    </div>
  </a>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Shortcut',
  props: {
    noBackground: Boolean,
    value: Object,
  },
});
</script>
