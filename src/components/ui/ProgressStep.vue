<template>
  <div class="progress__step">
    <slot name="header" />
    <div class="ps__stepper row radius-sm q-my-sm">
      <div class="ps__blocks">
        <span>1</span>
      </div>
      <div class="ps__blocks">
        <span>2</span>
      </div>
      <div class="ps__blocks">
        <span>3</span>
      </div>
      <div class="ps__blocks">
        <span>4</span>
      </div>
      <div class="ps__blocks">
        <span>5</span>
      </div>
    </div>
    <slot name="caption" />
    <slot name="body" />
  </div>
</template>

<script>
import 'src/assets/styles/ui/ProgressStep.scss';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ProgressStep',
  props: {
    current: Number,
  },
  computed: {
    currentStep() {
      return this.current;
    },
  },
  watch: {
    currentStep() {
      console.log('change');
      this.printCurrent();
      this.setProgressClass(this.currentStep);
    },
  },
  methods: {
    setProgressClass(step) {
      if (step > 5) {
        step = 5;
      }

      const blocks = document.getElementsByClassName('ps__blocks');
      const currentBlock = blocks[step - 1].classList;
      if (!currentBlock.contains('--current')) {
        currentBlock.add('--current');
        if (step > 1) {
          for (let s = 0; s < step - 1; s += 1) {
            blocks[s].classList.add('--done');
          }
        }
      }
    },
  },
  mounted() {
    this.setProgressClass(this.currentStep);
  },
});
</script>
