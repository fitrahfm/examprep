<template>
  <div class="footer w-100 q-mb-md">
    <divider />
    <div class="row w-100 justify-between q-mt-sm q-px-md text-grey-8">
      <div class="row">
        <div class="footer__year q-mr-sm">
          <span>&#169; 2021</span>
        </div>
        <div class="footer__name q-mr-sm">
          <span>examprep.ai</span>
        </div>
        <div class="footer__additional__links row">
          <div v-for="(link, index) in footerLinks.left" :key="index"
            class="footer__link q-mr-sm">
            <a class="row items-center" :href="link.url">{{ link.name }}</a>
          </div>
        </div>
      </div>
      <div class="row">
        <div v-for="(link, index) in footerLinks.right" :key="index"
            class="footer__link --right">
            <a class="row items-center" :href="link.url">{{ link.name }}</a>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import Divider from 'components/ui/Divider.vue';

export default defineComponent({
  name: 'Footer',
  components: {
    Divider,
  },
  data() {
    return {
      footerLinks: {
        left: [{
          name: 'Privacy',
          url: '#',
        }, {
          name: 'Legal',
          url: '#',
        }, {
          name: 'FAQ',
          url: '#',
        }, {
          name: 'Contact',
          url: '#',
        }],
        right: [{
          name: 'Feedback',
          url: '#',
        }],
      },
    };
  },
});
</script>
