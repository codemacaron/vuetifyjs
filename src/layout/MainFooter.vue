<template lang="pug">
  footer.footer(:class="{ [`footer-${type}`]: type }" :data-background-color="backgroundColor")
    .container
      nav
        ul
          li
            a(href="https://www.creative-tim.com") Creative Tim
          li
            a(href="https:///presentation.creative-tim.com") About Us
          li
            a(href="https:///blog.creative-tim.com") Blog
          li
            a(href="https://www.creative-tim.com/license") Licenses
      .copyright 
        | &copy; {{ year }}, made with 
        md-icon favorite
        | by
        a(href="https://www.creative-tim.com/" target="_blank") Creative Tim
        | for a better web.
</template>
<script>
export default {
  props: {
    backgroundColor: String,
    type: String
  },
  data() {
    return {
      year: new Date().getFullYear()
    };
  }
};
</script>
<style></style>
