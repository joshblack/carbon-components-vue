<template>
  <svg class="cv-icon">
    <use :xlink:href="iconHref"></use>
  </svg>
</template>

<script>
const spritePath = require('carbon-icons/dist/carbon-icons.svg');

export default {
  name: 'CvIcon',
  props: {
    href: { type: String, required: true },
  },
  computed: {
    iconHref() {
      if (this.href.toLowerCase().startsWith('cv(')) {
        return `${spritePath}#${this.href.substring(3, this.href.length - 1)}`;
      }
      return this.href;
    },
  },
};
</script>
