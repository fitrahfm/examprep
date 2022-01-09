<template>
  <q-card flat class="radius-sm q-mb-md q-px-md q-py-md"
    :class="[(size ? ('w-' + size) : ''), (color ? ('bg-' + color) : '')]"
  >
    <div v-show="!noHeader" class="cards__header row">
      <div class="col-11">
        <div class="cards__title">
          <span>{{ title }}</span>
        </div>
        <div class="cards__description">
          <span class="text-grey-7">
            {{ desc }}
          </span>
        </div>
      </div>
      <div v-show="tooltips" class="col-1 row justify-end items-center">
        <q-btn flat class="q-px-xs q-py-none" size="10px">
          <q-icon name="o_help_outline" />
        </q-btn>
      </div>
      <slot name="header" />
    </div>
    <divider v-show="!noHeader && !noDivider" />
    <div class="cards__content">
      <div v-show="$slots['body-top']" class="row justify-center text-grey-8">
        <slot name="body-top" />
      </div>
      <slot name="body" />
      <div v-show="$slots['body-bottom']" class="w-100">
        <slot name="body-bottom" />
      </div>
    </div>
  </q-card>
</template>

<script>
import { defineComponent } from 'vue';
import Divider from './Divider.vue';

export default defineComponent({
  name: 'CardWrapper',
  components: {
    Divider,
  },
  props: {
    size: String,
    title: String,
    desc: String,
    color: String,
    tooltips: Boolean,
    noDivider: Boolean,
    noHeader: Boolean,
  },
});
</script>
