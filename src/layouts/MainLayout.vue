<template>
  <q-layout view="hHh lpr fFf">
    <q-page-container>
      <div class="row">
        <exam-prep-header />
      </div>
      <div class="page__header q-py-lg q-px-lg">
        <div class="page__title q-mb-sm">
          <h5>Dashboard</h5>
        </div>
        <div class="page__description">
          <span class="text-grey-7">Financial Accounting and Reporting Exam Dashboard</span>
        </div>
      </div>
      <div class="row justify-center">
        <div class="col-8">
          <router-view class="q-py-lg" />
        </div>
      </div>
      <div class="row justify-center">
        <div class="col-8">
          <exam-prep-footer />
        </div>
      </div>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue';
import ExamPrepHeader from 'components/layout/Header.vue';
import ExamPrepFooter from 'components/layout/Footer.vue';

export default defineComponent({
  name: 'MainLayout',
  components: {
    ExamPrepHeader,
    ExamPrepFooter,
  },
  setup() {
    const leftDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
