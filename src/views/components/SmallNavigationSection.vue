<template lang="pug">
  .wrapper
    #menu
      .md-layout
        .md-layout-item.md-size-50.md-small-size-100
          .title
            h3 Menu
          md-toolbar.md-primary
            .md-toolbar-row
              .md-toolbar-section-start
                h3.md-title Menu
                md-list
                  md-list-item(href="#/")
                    p Link
                  md-list-item(href="javascript:void(0)")
                    p Link
                  li.md-list-item
                    a.md-list-item-router.md-list-item-container.md-button-clean.dropdown(href="javascript:void(0)")
                     .md-list-item-content
                        drop-down(direction="down")
                          md-button.md-button.md-button-link.md-white.md-simple.dropdown-toggle(slot="title" data-toggle="dropdown")
                            p Dropdown
                          ul.dropdown-menu(:class="{ 'dropdown-menu-right': responsive }")
                            li.dropdown-header Dropdown header
                            li
                              a.dropdown-item(href="#pablo") Action
                            li
                              a.dropdown-item(href="#pablo") Another action
                            li
                              a.dropdown-item(href="#pablo") Something else here
                            li.dropdown-divider
                            li
                              a.dropdown-item(href="#pablo") Separated link
                            li.dropdown-divider
                            li
                              a.dropdown-item(href="#pablo") One more separated link
              .md-toolbar-section-end
                md-button.md-just-icon.md-simple.md-white.md-toolbar-toggle
                  span.icon-bar
                  span.icon-bar
                  span.icon-bar
                .md-collapse
        .md-layout-item.md-size-50.md-small-size-100
          .title
            h3 Menu with Icons
          md-toolbar.md-info
            .md-toolbar-row
              .md-toolbar-section-start
                h3.md-title Icons
              .md-toolbar-section-end
                md-button.md-just-icon.md-simple.md-white.md-toolbar-toggle
                  span.icon-bar
                  span.icon-bar
                  span.icon-bar
                .md-collapse
                  md-list
                    md-list-item(href="javascript:void(0)")
                      md-icon email
                    md-list-item(href="javascript:void(0)")
                      md-icon face
                    li.md-list-item
                      a.md-list-item-router.md-list-item-container.md-button-clean.dropdown(href="javascript:void(0)")
                       .md-list-item-content
                          drop-down(direction="down")
                            md-button.md-button.md-button-link.md-white.md-simple.md-just-icon(slot="title" data-toggle="dropdown")
                              md-icon settings
                            ul.dropdown-menu.dropdown-menu-right
                              li.dropdown-header Dropdown header
                              li
                                a.dropdown-item(href="#pablo") Action
                              li
                                a.dropdown-item(href="#pablo") Another action
                              li
                                a.dropdown-item(href="#pablo") Something else here
                              li.dropdown-divider
                              li
                                a.dropdown-item(href="#pablo") Separated link
                              li.dropdown-divider
                              li
                                a.dropdown-item(href="#pablo") One more separated link
      .title
        h3 Navigation
</template>

<script>
export default {
  data() {
    return {
      responsive: false
    };
  },
  methods: {
    onResponsiveInverted() {
      if (window.innerWidth < 500) {
        this.responsive = true;
      } else {
        this.responsive = false;
      }
    }
  },
  mounted() {
    this.onResponsiveInverted();
    window.addEventListener("resize", this.onResponsiveInverted);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.onResponsiveInverted);
  }
};
</script>

<style lang="css"></style>
