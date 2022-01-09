<template>
  <div class="concept__mastery column">
    <div class="concept__title q-my-sm">
      <span>
        {{ value.conceptTitle }}
      </span>
    </div>
    <div class="mastery__estimate q-my-sm row w-100 no-wrap">
      <div class="sub__concept" v-for="(v, i) in value.subs" :key="i">
        <div class="sub__block" :class="v.active ? '--active' : ''">
          <q-tooltip class="sub__tooltip no-padding" max-width="150px"
            anchor="center right" self="center left"
            :offset="[10, 10]"
          >
            <div class="tooltip__title q-pa-sm bg-grey-3" style="width: 100%;">
              <span class="text-grey-8">
                {{ v.title }}
              </span>
            </div>
            <div class="tooltip__content">
              <div class="q-ma-sm">
                <span class="text-grey-9">
                  <b>
                    {{ v.estimate }}
                  </b>
                </span>
              </div>
              <div class="q-ma-sm">
                <span class="text-grey-7">
                  {{ v.caption }}
                </span>
              </div>
            </div>
          </q-tooltip>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ConceptMastery',
  props: {
    value: Object,
  },
});
</script>
