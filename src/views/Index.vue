<template lang="pug">
  .wrapper
    parallax.section.page-header.header-filter(:style="headerStyle")
      .container
        .md-layout
          .md-layout-item.md-size-50.md-small-size-70.md-xsmall-size-100
            h1.title
              | 징검다리 휴일
              br
              | 완벽하게 즐기기
            h4
              | 샌드위치 휴일이라고 슬퍼하기엔 이르다! 재미있게 즐기는 비법은?
            br
            md-button.md-success.md-lg(href="https://www.youtube.com/watch?v=dQw4w9WgXcQ" target="_blank")
              i.fas.fa-play
              | Watch video
    .main.main-raised
      .section
        .container
          .features.text-center
            .md-layout
              .md-layout-item.md-size-25.md-small-size-50.md-xsmall-size-100(v-for="item in content")
                .info
                  .md-layout-item.md-size-100.mx-auto
                    img.img-raised.img-fluid(:src="item.img" :alt="item.title")
                  .text-content
                    h4.info-title {{item.title}}
                    h5 {{item.price}} 원
                    p {{item.content}}
            p.last-list 리스트가 더이상 없습니다.
            md-button.md-primary(@click="getList()") 리스트 더보기 
      //- .section.text-center
        .container
          h2.title
            | Here is our team
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
                      small.card-description.text-muted
                        | Model
                    md-card-content
                      p.card-description
                        | You can write here details about one of your team members. You can give more details about what they do. Feel free to add some 
                        a( href="#") links
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
                      p.card-description
                        | You can write here details about one of your team members. You can give more details about what they do. Feel free to add some 
                        a(href="#") links
                        | for people to be able to follow them outside the site.
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
                      | Kendall Jenner
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
      //- .section.section-contacts
        .container
          .md-layout
            .md-layout-item.md-size-66.md-xsmall-size-100.mx-auto
              h2.text-center.title Work with us
              h4.text-center.description
                | Divide details about your product or agency work into parts. Write a few lines about each one and contact us about any further collaboration. We will responde get back to you in a couple of hours.
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
import axios from 'axios'
import ListData from './../assets/list.json'
import { log } from 'util';
export default {
  bodyClass: "landing-page",
  props: {
    header: {
      type: String,
      default: "https://cdn.pixabay.com/photo/2013/02/21/19/06/beach-84533_1280.jpg"
    },
    teamImg1: {
      type: String,
      default: require("@/assets/img/onepice/1.png")
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
      message: null,
      content: ListData,
      bottom: false,
      num: 1
    };
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.header})`
      };
    }
  },
  methods: {
    // 페이지의 맨 아래인지 확인하는 부분
    bottomVisible () {
      var scrollY = window.pageYOffset
      var visible = document.documentElement.clientHeight
      var pageHeight = document.documentElement.scrollHeight
      var bottomOfPage = visible + scrollY >= pageHeight
      console.log(bottomOfPage || pageHeight < visible)
      return bottomOfPage || pageHeight < visible
    },
    // 페이지 맨 아래라면 리스트 불러오기
    infiniteScroll () {
      window.addEventListener('scroll', () => {
        this.bottom = this.bottomVisible()
        if (this.bottom) {
          this.getList()
        }
      })
    },
    getList(){
      let Api = 'https://comento.cafe24.com/request.php?page=' + this.num + '&ord=asc'
        axios.get(Api).then((response) => {
          this.content.push(response.data.list)
          console.log(response.data.list)
          this.num++
        }).catch(error => console.error('실행실패 ::: ', error.message))
    }
  },
  created () {
    // this.infiniteScroll()
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
