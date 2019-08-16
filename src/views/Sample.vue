<template lang="pug">
  .wrapper
    parallax.page-header.header-filter(:style="headerStyle")
      .md-layout
        .md-layout-item
          .image-wrapper
            img.leaf4(:src="leaf4" alt="leaf4" v-show="leafShow")
            img.leaf3(:src="leaf3" alt="leaf3" v-show="leafShow")
            img.leaf2(:src="leaf2" alt="leaf2" v-show="leafShow")
            img.leaf1(:src="leaf1" alt="leaf1" v-show="leafShow")
            .brand
              h1 Vue Material Kit
              h3 A Badass Vue.js UI Kit made with Material Design.
    .main.main-raised
      .section.section-basic
        .container
          .title
            h2 Basic Elements
          basic-elements
      .section.section-navbars
        .container
          small-navigation
        navigation
      .section.section-tabs
        .container
          tabs
      .section.section-white
        .container
          nav-pills
      .section.section-notifications
        .container
          .title
            h3 Notifications
        notifications
      .section
        .container
          typography-images
      .section.section-javascript
        .container
          javascript-components
      .section
        .container.text-center
          .md-layout
            .md-layout-item.md-size-66.md-xsmall-size-100.ml-auto.mr-auto.text-center
              h2 Completed with examples
              h4 The kit comes with three pre-built pages to help you get started faster. You can change the text and images and you're good to go. More importantly, looking at them will give you a picture of what you can built with this powerful kit.
      .section.section-signup.page-header(:style="signupImage")
        .container
          .md-layout
            .md-layout-item.md-size-33.md-medium-size-40.md-small-size-50.md-xsmall-size-70.mx-auto.text-center
              login-card(header-color="green")
                h4.card-title(slot="title") Login
                md-button.md-just-icon.md-simple.md-white(slot="buttons" href="javascript:void(0)")
                  i.fab.fa-facebook-square
                md-button.md-just-icon.md-simple.md-white
                  slot="buttons"
                  href="javascript:void(0)"
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
                md-button.md-simple.md-success.md-lg(slot="footer") Get Started
      .md-layout
        .md-layout-item.text-center
          md-button.md-simple.md-success.md-lg(href="#/login") View Login Page
      .section.section-examples
        .container-fluid.text-center
          .md-layout
            .md-layout-item
              a(href="#/landing" target="_blank")
                img.img-raised.rounded.img-fluid(:src="landing" alt="Rounded Image")
              md-button.md-simple.md-success.md-lg(href="#/landing") View Landing Page
            .md-layout-item
              a(href="#/profile" target="_blank")
                img.img-raised.rounded.img-fluid(:src="profile" alt="Rounded Image")
              md-button.md-simple.md-success.md-lg(href="#/profile") View Profile Page
      .section.section-download#downloadSection
        .container
          .md-layout.text-center
            .md-layout-item.md-size-66.md-small-size-100.mx-auto
              h2 Do you love this UI Kit?
              h4 
                | Cause if you do, it can be yours for FREE. Hit the buttons below to navigate to our website where you can find the kit. Our friends from
                a(href="https://themeisle.com/?utm_campaign=mkfree-hestia&amp;utm_source=creativetim&amp;utm_medium=website" target="_blank") ThemeIsle
                | created a Wordpress Theme which can be also downloaded for free. Start a new project or give an old Bootstrap project a new look!
            .md-layout-item.md-size-50.md-small-size-100.mx-auto
              md-button.md-success.md-lg(href="https://www.creative-tim.com/product/material-kit" target="_blank")
                i.fab.fa-html5
                | Free HTML Download
              md-button.md-success.md-lg(href="https://themeisle.com/themes/hestia/?utm_campaign=mkfree-hestia&amp;utm_source=creativetim&amp;utm_medium=website" target="_blank")
                i.fab.fa-wordpress
                | Wordpress Theme
          .md-layout.text-center
            .md-layout-item.md-size-66.md-small-size-100.mx-auto
              h2 Want more?
              h4 We've just launched
                a(href="https://www.creative-tim.com/product/vue-material-dashboard-pro?ref=utp-mk-demos" target="_blank") Vue Material Dashboard PRO
                | and
                a(href="https://www.creative-tim.com/product/vue-material-kit-pro?ref=utp-vmk-demos" target="_blank") Vue Material Kit PRO
                | . Every product has a huge number of components, sections and example pages. Start Your Development With A Badass Bootstrap UI Kit inspired by Material Design.
            .md-layout-item.md-size-50.md-small-size-100.mx-auto
              .btn-container
                md-button.md-button.md-success.md-lg.md-upgrade(href="https://www.creative-tim.com/product/vue-material-kit-pro?ref=utp-vmk-demos" target="_blank") unarchive Vue Material Kit PRO
                md-button.md-button.md-success.md-lg.md-upgrade(href="https://www.creative-tim.com/product/vue-material-dashboard-pro?ref=utp-vmd-demos" target="_blank") unarchive Vue Material Dashboard PRO
          .sharing-area.text-center
            .md-layout
              .md-layout-item
                h3 Thank you for supporting us!
            md-button.md-twitter
              i.fab.fa-twitter
              | Tweet
            md-button.md-facebook
              i.fab.fa-facebook-square
              |  Share
            md-button.md-google
              i.fab.fa-google-plus
              |  Share
            md-button.md-github
              i.fab.fa-github
              |  Star
</template>

<script>
import BasicElements from "./components/BasicElementsSection";
import Navigation from "./components/NavigationSection";
import SmallNavigation from "./components/SmallNavigationSection";
import Tabs from "./components/TabsSection";
import NavPills from "./components/NavPillsSection";
import Notifications from "./components/NotificationsSection";
import TypographyImages from "./components/TypographyImagesSection";
import JavascriptComponents from "./components/JavascriptComponentsSection";
import { LoginCard } from "@/components";

export default {
  components: {
    BasicElements,
    Navigation,
    SmallNavigation,
    Tabs,
    NavPills,
    Notifications,
    TypographyImages,
    JavascriptComponents,
    LoginCard
  },
  name: "index",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("@/assets/img/vue-mk-header.jpg")
    },
    leaf4: {
      type: String,
      default: require("@/assets/img/leaf4.png")
    },
    leaf3: {
      type: String,
      default: require("@/assets/img/leaf3.png")
    },
    leaf2: {
      type: String,
      default: require("@/assets/img/leaf2.png")
    },
    leaf1: {
      type: String,
      default: require("@/assets/img/leaf1.png")
    },
    signup: {
      type: String,
      default: require("@/assets/img/city.jpg")
    },
    landing: {
      type: String,
      default: require("@/assets/img/landing.jpg")
    },
    profile: {
      type: String,
      default: require("@/assets/img/profile.jpg")
    }
  },
  data() {
    return {
      firstname: null,
      email: null,
      password: null,
      leafShow: false
    };
  },
  methods: {
    leafActive() {
      if (window.innerWidth < 768) {
        this.leafShow = false;
      } else {
        this.leafShow = true;
      }
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    },
    signupImage() {
      return {
        backgroundImage: `url(${this.signup})`
      };
    }
  },
  mounted() {
    this.leafActive();
    window.addEventListener("resize", this.leafActive);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.leafActive);
  }
};
</script>
<style lang="scss">
.section-download {
  .md-button + .md-button {
    margin-left: 5px;
  }
}

@media all and (min-width: 991px) {
  .btn-container {
    display: flex;
  }
}
</style>
