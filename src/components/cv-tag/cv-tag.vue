<template>
  <span class="bx--tag" :class="`bx--tag--${kind}`">{{label}}</span>
</template>

<script>
export default {
  name: 'CvTag',
  props: {
    label: String,
    kind: {
      type: String,
      validator(val) {
        return [
          'ibm',
          'beta',
          'third-party',
          'local',
          'dedicated',
          'custom',
          'experimental',
          'community',
          'private',
          'deprecated',
        ].includes(val);
      },
    },
  },
};
</script>

<style lang="scss">
// Import Style Definitions
@import '~carbon-components/scss/components/tag/tag';
</style>
