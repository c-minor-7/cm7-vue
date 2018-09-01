<template>
  <section ref="container"></section>
</template>

<script>
import Cm7 from 'cm7/dist/Cm7.es.js';
export default {
  props: {
    src: {
      type: String,
      required: true,
    },
  },

  watch: {
    src(src) {
      try {
        this.cm7 = new Cm7({ src });
        this.cm7Mount();
        this.$emit('error', false);
      } catch (e) {
        this.$emit('error', e);
      }
    },
  },

  data: () => ({
    cm7: null,
  }),

  created() {
    this.cm7 = new Cm7({
      src: this.src,
    });
  },

  mounted() {
    this.cm7Mount();
  },

  methods: {
    cm7Mount() {
      this.cm7.mount(this.$refs.container);
    },
  },
};
</script>

<style>
</style>
