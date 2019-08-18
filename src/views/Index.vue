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
      .section.text-center
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
      .section.section-contacts
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
      content: [
        {
          title: '모리 코튼 원피스',
          content: '잔잔한 패턴이 포인트인 반팔 원피스 입니다. 세련된 블루컬러에 적당한 길이감이 발랄하지만 소녀스러운 무드를 연출하게 한답니다.',
          price: '20000',
          img: require("@/assets/img/onepice/1.png")
        },
        {
          title: 'Flexmill 도어스토퍼 & 도어행어',
          content: '자연의 바람길을 열어주는 도어스토퍼! 도어스토퍼로 사용하지 않을 때는당신의 휴식을 위한 도어 행어로 사용해 보세요~ 플렉스밀 도어스토퍼는 간결한 디자인으로 어느 인테리어에나 잘 어우러지는 감각적인 디자인입니다.최상급 실리콘 재질 ( 유럽안전인증 )을 사용함으로서 안전한 위생관리가 가능합니다.',
          price: '12000',
          img: require("@/assets/img/onepice/2.png")
        },
        {
          title: '웰스테일 임신다이어리/출산 태교일기',
          content: '사랑하는 내 아기를 위해 준비하는 특별한 선물 웰스테일 태교 일기장과 만나보세요.',
          price: '25000',
          img: require("@/assets/img/onepice/3.png")
        },
        {
          title: '[스토] 키즈 에바 슬라이드 아이바캉스타',
          content: '데일리 슈즈로 너무 좋은 가볍고 편안한 샌들 입니다. 초경량으로 가볍고 신고 벗기기가 편안합니다. 물기에 강하여 빠른 건조가 되어, 일상뿐만 아니라 물놀이시 비오는 날 등 여름에 데일리로 신기 좋은 샌들입니다.',
          price: '32000',
          img: require("@/assets/img/onepice/4.png")
        },
        {
          title: '펜토미노 3종 SET(교구1세트+교재3권)',
          content: '미취학 아동부터 초등학생에게 꼭 필요한 사고력 향상 교구 교재 세트로 초등교과 과정에도 연계되는 필수 교구 입니다.',
          price: '12000',
          img: require("@/assets/img/onepice/5.png")
        },
        {
          title: '자외선차단 유아 물안경',
          content: '깜찍한 캐릭터 디자인이 포인트인 개성 넘치는 물안경입니다. UV 차단 기능과 함께 렌즈 내부에 안티포그 코팅이 되어있어 김서림 방지가 되어 물놀이 시 항상 깨끗한 시야를 유지 할 수 있습니다.',
          price: '12000',
          img: require("@/assets/img/onepice/6.png")
        },
        {
          title: '[키두]어린이 안전벨트 인형 허그돌',
          content: '허그돌(Hugdoll)은 어린이 안전벨트 인형으로, 성인의 체형에 맞춰진 기존의 안전벨트를 그대로 매기에도, 영유아를 위한 카시트를 타기에도 부적절한 5-12세 어린이들을 위해 탄생한 제품입니다. 허그돌은 어린이들에게 신체적으로, 정서적으로 불편한 기존의 안전벨트를 보다 편안하고 즐겁게 착용할 수 있도록 도와주어 안전벨트 착용에 대한 긍정적인 경험을 제공합니다.',
          price: '12000',
          img: require("@/assets/img/onepice/7.png")
        },
        {
          title: '캐릭터컬러비치타올1+1',
          content: '물놀이 후 추위 또는 해변에서의 몸에 붙는 모래때문에 스트레스 받으셨죠? 비치타올로 몸을 감싸 추의도 막고, 모래 위 비치타올을 깔아 몸에 모래가 붙는 것도 방지해보세요.',
          price: '12000',
          img: require("@/assets/img/onepice/8.png")
        },
        {
          title: '항균 피피티피 만들기(색상선택)',
          content: '기저귀 갈 때 조심~ 조심 아차 싶을 땐 이미 늦죠. 주변이 시원해지면 여지없이 발싸 하는 오줌세례 요럴때 사용하세요.',
          price: '12000',
          img: require("@/assets/img/onepice/9.png")
        },
        {
          title: '시팅튜브 라이언',
          content: '라이언과 함께 놀자 시팅튜브 신나는 썸머 바캉스를 위한 핫한 잇템, 준비되셨나요? 수영장에서 시선을 집중시킬 잇템들을 원한다면 튜브맛집 카카오프렌즈에서 준비한 2019 여름 신상 튜브를 만나보세요! 모두 튜브 쇼핑하러 GOGO!',
          price: '12000',
          img: require("@/assets/img/onepice/10.png")
        },
      ]
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
