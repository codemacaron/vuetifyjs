<template lang="pug">
  .wrapper
    #javascriptComponents
      .title
        h2 Javascript components
      .md-layout
        .md-layout-item.md-small-size-100
          .title
            h3 Modal
          .md-layout
            .md-layout-item.md-size-33
              md-button.md-success.md-block(@click="classicModal = true")
                md-icon library_books
                | Classic
              modal(v-if="classicModal" @close="classicModalHide")
                template(slot="header")
                  h4.modal-title Modal Title
                  md-button.md-simple.md-just-icon.md-round.modal-default-button(@click="classicModalHide")
                    md-icon clear
                template(slot="body")
                  p Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. A small river named Duden flows by their place and supplies it with the necessary regelialia. It is a paradisematic country, in which roasted parts of sentences fly into your mouth. Even the all-powerful Pointing has no control about the blind texts it is an almost unorthographic life One day however a small line of blind text by the name of Lorem Ipsum decided to leave for the far World of Grammar.
                template(slot="footer")
                  md-button.md-simple Nice Button
                  md-button.md-danger.md-simple(@click="classicModalHide") Close
          .md-layout
            .md-layout-item.md-size-80
              .title
                h3 DatePicker
              md-datepicker(v-model="selectedDate")
                label Select date
        .md-layout-item.md-small-size-100
          .title
            h3 Popovers
          .md-layout
            .md-layout-item
              v-popover(offset="8" placement="left")
                md-button On left
                template(slot="popover")
                  h3.popover-header Popover on left
                  .popover-body Here will be some very useful information about his popover. Here will be some very useful information about his popover.
              v-popover(offset="4" placement="top")
                md-button On top
                template(slot="popover")
                  h3.popover-header Popover on top
                  .popover-body Here will be some very useful information about his popover.
              v-popover(offset="4" placement="bottom")
                md-button On bottom
                template(slot="popover")
                  h3.popover-header Popover on bottom
                  .popover-body Here will be some very useful information about his popover.
              v-popover(offset="8" placement="right")
                md-button On right
                template(slot="popover")
                  h3.popover-header Popover on right
                  .popover-body Here will be some very useful information about his popover.
          .md-layout#tooltips
            .md-layout-item
              .title
                h3 Tooltips
              md-button 
                | on left
                md-tooltip(md-direction="left") Tooltip on left
              md-button 
                | on top
                md-tooltip(md-direction="top") Tooltip on top
              md-button 
                | on bottom
                md-tooltip(md-direction="bottom") Tooltip on bottom
              md-button 
                | on right
                md-tooltip(md-direction="right") Tooltip on right
      br
      .title
        h3 Carousel
      .md-layout
        .md-layout-item.md-size-66.mx-auto.md-small-size-100
          md-card
            carousel(:per-page="1" loop :speed="700" autoplay :autoplay-timeout="5000" :mouse-drag="false" navigationEnabled navigationNextLabel="<i class='material-icons'>keyboard_arrow_right</i>" navigationPrevLabel="<i class='material-icons'>keyboard_arrow_left</i>")
              slide
                .carousel-caption
                  h4
                    md-icon location_on
                    | Somewhere Beyond, United States
                img(:src="carousel1" alt="carousel1")
              slide
                .carousel-caption
                  h4
                    md-icon location_on
                    | Yellowstone National Park, United States
                img(:src="carousel2" alt="carousel2")
              slide
                .carousel-caption
                  h4
                    md-icon location_on
                    | Yellowstone National Park, United States
                img(:src="carousel3" alt="carousel3")
</template>

<script>
import { Modal } from "@/components";
export default {
  components: {
    Modal
  },
  data() {
    return {
      classicModal: false,
      selectedDate: new Date("2018/03/26"),
      carousel1: require("@/assets/img/nature-2.jpg"),
      carousel2: require("@/assets/img/nature.jpg"),
      carousel3: require("@/assets/img/nature-3.jpg")
    };
  },
  methods: {
    classicModalHide() {
      this.classicModal = false;
    }
  }
};
</script>
