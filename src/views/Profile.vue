<template lang="pug">
  .wrapper
    parallax.section.page-header.header-filter(:style="headerStyle")
    .main main-raised
      .section.profile-content
        .container
          .md-layout
            .md-layout-item.md-size-50.mx-auto
              .profile
                .avatar
                  img.img-raised.rounded-circle.img-fluid(:src="img" alt="Circle Image")
                .name
                  h3.title Carla Hortensia
                  h6 Designer
                  md-button.md-just-icon.md-simple.md-dribbble(href="javascript:void(0)")
                    i.fab.fa-dribbble
                  md-button.md-just-icon.md-simple.md-twitter(href="javascript:void(0)")
                    i.fab.fa-twitter
                  md-button.md-just-icon.md-simple.md-pinterest(href="javascript:void(0)")
                    i.fab.fa-pinterest
          .description.text-center
            p An artist of considerable range, Chet Faker — the name taken by Melbourne-raised, Brooklyn-based Nick Murphy — writes, performs and records all of his own music, giving it a warm, intimate feel with a solid groove structure.
          .profile-tabs
            tabs(:tab-name="['Studio', 'Work', 'Favorite']" :tab-icon="['camera', 'palette', 'favorite']" plain nav-pills-icons color-button="success")
              template(slot="tab-pane-1")
                .md-layout
                  .md-layout-item.md-size-25.ml-auto
                    img.rounded(:src="tabPane1[0].image")
                    img.rounded(:src="tabPane1[1].image")
                  .md-layout-item.md-size-25.mr-auto
                    img.rounded(:src="tabPane1[3].image")
                    img.rounded(:src="tabPane1[2].image")
              template(slot="tab-pane-2")
                .md-layout
                  .md-layout-item.md-size-25.ml-auto
                    img.rounded(:src="tabPane2[0].image")
                    img.rounded(:src="tabPane2[1].image")
                    img.rounded(:src="tabPane2[2].image")
                  .md-layout-item.md-size-25.mr-auto
                    img.rounded(:src="tabPane2[3].image")
                    img.rounded(:src="tabPane2[4].image")
              template(slot="tab-pane-3")
                .md-layout
                  .md-layout-item.md-size-25.ml-auto
                    img.rounded(:src="tabPane3[0].image")
                    img.rounded(:src="tabPane3[1].image")
                  .md-layout-item.md-size-25.mr-auto
                    img.rounded(:src="tabPane3[2].image")
                    img.rounded(:src="tabPane3[3].image")
                    img.rounded(:src="tabPane3[4].image")
</template>

<script>
import { Tabs } from "@/components";
export default {
  components: {
    Tabs
  },
  bodyClass: "profile-page",
  data() {
    return {
      tabPane1: [
        { image: require("@/assets/img/examples/studio-1.jpg") },
        { image: require("@/assets/img/examples/studio-2.jpg") },
        { image: require("@/assets/img/examples/studio-4.jpg") },
        { image: require("@/assets/img/examples/studio-5.jpg") }
      ],
      tabPane2: [
        { image: require("@/assets/img/examples/olu-eletu.jpg") },
        { image: require("@/assets/img/examples/clem-onojeghuo.jpg") },
        { image: require("@/assets/img/examples/cynthia-del-rio.jpg") },
        { image: require("@/assets/img/examples/mariya-georgieva.jpg") },
        { image: require("@/assets/img/examples/clem-onojegaw.jpg") }
      ],
      tabPane3: [
        { image: require("@/assets/img/examples/mariya-georgieva.jpg") },
        { image: require("@/assets/img/examples/studio-3.jpg") },
        { image: require("@/assets/img/examples/clem-onojeghuo.jpg") },
        { image: require("@/assets/img/examples/olu-eletu.jpg") },
        { image: require("@/assets/img/examples/studio-1.jpg") }
      ]
    };
  },
  props: {
    header: {
      type: String,
      default: require("@/assets/img/city-profile.jpg")
    },
    img: {
      type: String,
      default: require("@/assets/img/faces/christian.jpg")
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

<style lang="scss" scoped>
.section {
  padding: 0;
}

.profile-tabs /deep/ {
  .md-card-tabs .md-list {
    justify-content: center;
  }

  [class*="tab-pane-"] {
    margin-top: 3.213rem;
    padding-bottom: 50px;

    img {
      margin-bottom: 2.142rem;
    }
  }
}
</style>
