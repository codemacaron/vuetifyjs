<template lang="pug">
  .wrapper
    #navigation
      .navigation-example(:style="bgImage")
        .md-layout
          .md-layout-item
            md-toolbar.md-rose
              .md-toolbar-row
                .md-toolbar-section-start
                  h3.md-title Brand
                  md-list
                    md-list-item(href="#/")
                      p Link
                    md-list-item(href="javascript:void(0)")
                      p Link
                .md-toolbar-section-end
                  md-button.md-just-icon.md-simple.md-white.md-toolbar-toggle
                    span.icon-bar
                    span.icon-bar
                    span.icon-bar
                  .md-collapse
                    .md-autocomplete
                      md-autocomplete.search.has-white(v-model="selectedEmployee" :md-options="employees" :md-open-on-focus="false")
                        label Search...
            md-toolbar.md-info
              .md-toolbar-row
                .md-toolbar-section-start
                  h3.md-title Info Color
                .md-toolbar-section-end
                  md-button.md-just-icon.md-simple.md-white.md-toolbar-toggle
                    span.icon-bar
                    span.icon-bar
                    span.icon-bar
                  .md-collapse
                    md-list
                      md-list-item(href="#/")
                        p Discover
                      md-list-item(href="javascript:void(0)")
                        p Profile
                      md-list-item(href="javascript:void(0)")
                        p Settings
            md-toolbar.md-primary
              .md-toolbar-row
                .md-toolbar-section-start
                  h3.md-title Primary Color
                .md-toolbar-section-end
                  md-button.md-just-icon.md-simple.md-white.md-toolbar-toggle
                    span.icon-bar
                    span.icon-bar
                    span.icon-bar
                  .md-collapse
                    md-list
                      md-list-item(href="#/")
                        md-icon explore
                        p Discover
                      md-list-item(href="javascript:void(0)")
                        md-icon account_circle
                        p Profile
                      md-list-item(href="javascript:void(0)")
                        md-icon settings
                        p Settings
            md-toolbar.md-dark
              .md-toolbar-row
                .md-toolbar-section-start
                  h3.md-title Navbar with notification
                .md-toolbar-section-end
                  md-button.md-just-icon.md-simple.md-white.md-toolbar-toggle
                    span.icon-bar
                    span.icon-bar
                    span.icon-bar
                  .md-collapse
                    md-list
                      md-list-item(href="javascript:void(0)")
                        p Discover
                      md-list-item(href="javascript:void(0)")
                        p Whishlist
                      li.md-list-item
                        a.md-list-item-router.md-list-item-container.md-button-clean(href="javascript:void(0)")
                          .md-list-item-content
                            md-button.md-rose.md-just-icon.md-round
                              md-icon email
                      li.md-list-item
                        a.md-list-item-router.md-list-item-container.md-button-clean.dropdown(href="javascript:void(0)")
                          .md-list-item-content
                            drop-down.profile-photo(direction="down")
                              .profile-photo-small(slot="title" data-toggle="dropdown")
                                img(:src="img" alt="Circle Image")
                              ul.dropdown-menu.dropdown-menu-right
                                li.dropdown-headerDropdown header
                                  a.dropdown-item(href="#pablo") Me
                                li
                                  a.dropdown-item(href="#pablo") Settings and other stuff
                                li
                                  a.dropdown-item(href="#pablo") Sign Out
            md-toolbar.md-white
              .md-toolbar-row
                .md-toolbar-section-start
                  h3.md-title Navbar with profile
                .md-toolbar-section-end
                  md-button.md-just-icon.md-simple.md-white.md-toolbar-toggle
                    span.icon-bar
                    span.icon-bar
                    span.icon-bar
                  .md-collapse
                    md-list
                      md-list-item(href="javascript:void(0)")
                        p Discover
                      md-list-item(href="javascript:void(0)")
                        p Whishlist
                      li.md-list-item
                        a.md-list-item-router.md-list-item-container.md-button-clean(href="javascript:void(0)")
                          .md-list-item-content
                            md-button.md-rose.md-round Register
            md-toolbar.md-transparent
              .md-toolbar-row
                .md-toolbar-section-start
                  h3.md-title Transparent
                .md-toolbar-section-end
                  md-button.md-just-icon.md-simple.md-white.md-toolbar-toggle
                    span.icon-bar
                    span.icon-bar
                    span.icon-bar
                  .md-collapse
                    md-list
                      md-list-item(href="javascript:void(0)")
                        i.fab.fa-facebook-square
                        p Facebook
                      md-list-item(href="javascript:void(0)")
                        i.fab.fa-twitter
                        p Twitter
                      md-list-item(href="javascript:void(0)")
                        i.fab.fa-instagram
                        p Instagram
</template>

<script>
export default {
  data() {
    return {
      selectedEmployee: "",
      employees: [
        "Jim Halpert",
        "Dwight Schrute",
        "Michael Scott",
        "Pam Beesly",
        "Angela Martin",
        "Kelly Kapoor",
        "Ryan Howard",
        "Kevin Malone"
      ]
    };
  },
  props: {
    image: {
      type: String,
      default: require("@/assets/img/bg.jpg")
    },
    img: {
      type: String,
      default: require("@/assets/img/faces/avatar.jpg")
    }
  },
  computed: {
    bgImage() {
      return {
        backgroundImage: `url(${this.image})`
      };
    }
  }
};
</script>

<style lang="css"></style>
