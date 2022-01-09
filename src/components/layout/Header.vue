<template>
  <q-header reveal elevated class="bg-white text-black" height-hint="98">
    <q-toolbar>
      <div class="col-2">
        <div class="q-pl-lg q-pr-xl q-py-md">
          <img class="w-100" :src="examPrepLogo" />
        </div>
      </div>
    </q-toolbar>
  </q-header>
</template>

<script>
import { defineComponent } from 'vue';
import Logo from 'assets/ep-logo.png';

export default defineComponent({
  name: 'Header',
  data() {
    return {
      examPrepLogo: Logo,
    };
  },
});
</script>
