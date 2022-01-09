<template>
  <card-wrapper no-header color="grey-2" size="55" class="q-my-md">
    <template v-slot:body-top>
      <span>Resume Learning</span>
    </template>
    <template v-slot:body>
      <div class="last__lesson column no-wrap justify-center items-center q-mt-lg"
        style="height: 135px"
      >
        <q-avatar rounded class="q-mb-md" color="white" size="xl"
          icon="directions"
          text-color="blue-6"
          font-size="30px"
        />
        <div class="last__lesson caption text-center text-grey-8 w-80">
          <span>
            Balance sheet / statement of finantial position
          </span>
        </div>
      </div>
    </template>
    <template v-slot:body-bottom>
      <div class="row justify-end">
        <q-btn flat dense no-caps color="blue-8">
          <span>Resume</span>
          <q-icon size="10px" name="o_arrow_forward" />
        </q-btn>
      </div>
    </template>
  </card-wrapper>
</template>

<script>
import { defineComponent } from 'vue';
import CardWrapper from 'components/ui/CardWrapper.vue';

export default defineComponent({
  name: 'CurrentCourse',
  components: {
    CardWrapper,
  },
});
</script>
