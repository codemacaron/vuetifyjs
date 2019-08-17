<template lang="pug">
  .wrapper
    .section.page-header.header-filter(:style="headerStyle")
      .container
        .md-layout
          .md-layout-item.md-size-33.md-small-size-66.md-xsmall-size-100.md-medium-size-40.mx-auto
            login-card(header-color="green")
              h4.card-title(slot="title") Login
              md-button.md-just-icon.md-simple.md-white(slot="buttons" href="javascript:void(0)")
                i.fab.fa-facebook-square
              md-button.md-just-icon.md-simple.md-white(slot="buttons" href="javascript:void(0)")
                i.fab.fa-twitter
              md-button.md-just-icon.md-simple.md-white(slot="buttons" href="javascript:void(0)")
                i.fab.fa-google-plus-g
              p.description(slot="description") Or Be Classical
              md-field.md-form-group(slot="inputs")
                md-icon face
                label First Name...
                md-input(v-model="firstname")
              md-field.md-form-group(slot="inputs")
                md-icon email
                label Email...
                md-input(v-model="email" type="email")
              md-field.md-form-group(slot="inputs")
                md-icon lock_outline
                label Password...
                md-input(v-model="password")
              md-button.md-simple.md-success.md-lg(slot="footer")
                Get Started
</template>

<script>
import { LoginCard } from "@/components";

export default {
  components: {
    LoginCard
  },
  bodyClass: "login-page",
  data() {
    return {
      firstname: null,
      email: null,
      password: null
    };
  },
  props: {
    header: {
      type: String,
      default: require("@/assets/img/profile_city.jpg")
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.header})`
      };
    }
  }
};
</script>

<style lang="css"></style>
