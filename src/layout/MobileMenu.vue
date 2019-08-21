<template lang="pug">
  md-list.nav-mobile-menu.nav-mobile-section-start(v-if="navMobileSectionStart === 'true'")
    slot
</template>

<script>
export default {
  name: "mobile-menu",
  props: {
    navMobileSectionStart: {
      type: String,
      default: "false"
    }
  }
};
</script>
