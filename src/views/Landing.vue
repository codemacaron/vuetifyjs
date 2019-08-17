<template lang="pug">
  .wrapper
    parallax.section.page-header.header-filter(:style="headerStyle")
      .container
        .md-layout
          .md-layout-item.md-size-50.md-small-size-70.md-xsmall-size-100
            h1.title Your Story Starts With Us.
            h4 Every landing page needs a small description after the big bold title, that's why we added this text here. Add here all the information that can make you or your product create the first impression.
            br
            md-button.md-success.md-lg(href="https://www.youtube.com/watch?v=dQw4w9WgXcQ" target="_blank")
              i.fas.fa-play
              | Watch video
    .main.main-raised
      .section
        .container
          .md-layout
            .md-layout-item.md-size-66.md-xsmall-size-100.mx-auto.text-center
              h2.title.text-center Let's talk product
              h5.description This is the paragraph where you can write more details about your product. Keep you user engaged by providing meaningful information. Remember that by this time, the user is curious, otherwise he wouldn't scroll to get here. Add a button if you want the user to see more.
          .features.text-center
            .md-layout
              .md-layout-item.md-medium-size-33.md-small-size-100
                .info
                  .icon.icon-info
                    md-icon chat
                  h4.info-title Free Chat
                  p Divide details about your product or agency work into parts. Write a few lines about each one. A paragraph describing a feature will be enough.
              .md-layout-item.md-medium-size-33.md-small-size-100
                .info
                  .icon.icon-success
                    md-icon verified_user
                  h4.info-titleVerified Users
                  p Divide details about your product or agency work into parts. Write a few lines about each one. A paragraph describing a feature will be enough.
              .md-layout-item.md-medium-size-33.md-small-size-100
                .info
                  .icon.icon-danger
                    md-icon fingerprint
                  h4.info-title Fingerprint
                  p Divide details about your product or agency work into parts. Write a few lines about each one. A paragraph describing a feature will be enough.
      .section.text-center
        .container
          h2.title Here is our team
          .team
            .md-layout
              .md-layout-item.md-medium-size-33.md-small-size-100
                .team-player
                  md-card.md-card-plain
                    .md-layout-item.md-size-50.mx-auto
                      img.img-raised.rounded-circle.img-fluid(:src="teamImg1" alt="Thumbnail Image")
                    h4.card-title
                      | Gigi Hadid
                      br
                      small.card-description.text-muted Model
                    md-card-content
                      p.card-description
                        | You can write here details about one of your team members. You can give more details about what they do. Feel free to add some
                        a(href="#") links 
                        | for people to be able to follow them outside the site.
                    md-card-actions.text-center
                      md-button.md-just-icon.md-simple(href="javascript:void(0)")
                        i.fab.fa-twitter
                      md-button.md-just-icon.md-simple(href="javascript:void(0)")
                        i.fab.fa-instagram
                      md-button.md-just-icon.md-simple(href="javascript:void(0)")
                        i.fab.fa-facebook-square
              .md-layout-item.md-medium-size-33.md-small-size-100
                .team-player
                  md-card.md-card-plain
                    .md-layout-item.md-size-50.mx-auto
                      img.img-raised.rounded-circle.img-fluid(:src="teamImg2" alt="Thumbnail Image")
                    h4.card-title
                      | Carla Hortensia
                      br
                      small.card-description.text-muted Designer
                    md-card-content
                      p.card-description You can write here details about one of your team members. You can give more details about what they do. Feel free to add some <a href="#">links</a> for people to be able to follow them outside the site.
                    md-card-actions.text-center
                      md-button.md-just-icon.md-simple(href="javascript:void(0)")
                        i.fab.fa-twitter
                      md-button.md-just-icon.md-simple(href="javascript:void(0)")
                        i.fab.fa-linkedin
              .md-layout-item.md-medium-size-33.md-small-size-100
                .team-player
                  md-card.md-card-plain
                    .md-layout-item.md-size-50.mx-auto
                      img.img-raised.rounded-circle.img-fluid(:src="teamImg3" alt="Thumbnail Image")
                    h4.card-title 
                      Kendall Jenner
                      br
                      small.card-description.text-muted Model
                    md-card-content
                      p.card-description 
                        | You can write here details about one of your team members. You can give more details about what they do. Feel free to add some
                        a(href="#") links
                        | for people to be able to follow them outside the site.
                    md-card-actions.text-center
                      md-button.md-just-icon.md-simple(href="javascript:void(0)")
                        i.fab.fa-twitter
                      md-button.md-just-icon.md-simple(href="javascript:void(0)")
                        i.fab.fa-instagram
                      md-button.md-just-icon.md-simple(href="javascript:void(0)")
                        i.fab.fa-facebook-square
      .section.section-contacts
        .container
          .md-layout
            .md-layout-item.md-size-66.md-xsmall-size-100.mx-auto
              h2.text-center.title Work with us
              h4.text-center.description Divide details about your product or agency work into parts. Write a few lines about each one and contact us about any further collaboration. We will responde get back to you in a couple of hours.
              form.contact-form
                .md-layout
                  .md-layout-item.md-size-50
                    md-field
                      label Your Name
                      md-input(v-model="name" type="text")
                  .md-layout-item.md-size-50
                    md-field
                      label Your Email
                      md-input(v-model="email" type="email")
                md-field(maxlength="5")
                  label Your Message
                  md-textarea(v-model="message")
                .md-layout
                  .md-layout-item.md-size-33.mx-auto.text-center
                    md-button.md-success Send Message
</template>

<script>
export default {
  bodyClass: "landing-page",
  props: {
    header: {
      type: String,
      default: require("@/assets/img/bg7.jpg")
    },
    teamImg1: {
      type: String,
      default: require("@/assets/img/faces/avatar.jpg")
    },
    teamImg2: {
      type: String,
      default: require("@/assets/img/faces/christian.jpg")
    },
    teamImg3: {
      type: String,
      default: require("@/assets/img/faces/kendall.jpg")
    }
  },
  data() {
    return {
      name: null,
      email: null,
      message: null
    };
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

<style lang="scss" scoped>
.md-card-actions.text-center {
  display: flex;
  justify-content: center !important;
}
.contact-form {
  margin-top: 30px;
}

.md-has-textarea + .md-layout {
  margin-top: 15px;
}
</style>
