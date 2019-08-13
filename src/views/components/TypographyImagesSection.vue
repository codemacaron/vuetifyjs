<template lang="pug">
  .wrapper 
    #typography 
      .title 
        h2 Typography
      
      .md-layout 
        .md-layout-item 
          .tim-typo 
            h1
              span.tim-note 
                Header 1
              | The Life of Material Kit
          .tim-typo 
            h2 
              span.tim-note 
                Header 2
              | The Life of Material Kit
          .tim-typo 
            h3
              span.tim-note 
                Header 3
              | The Life of Material Kit
          
          .tim-typo 
            h4
              span.tim-note 
                Header 4
              | The Life of Material Kit
          .tim-typo 
            h5
              span.tim-note 
                Header 5
              | The Life of Material Kit
          
          .tim-typo 
            h6
              span.tim-note 
                Header 6
              | The Life of Material Kit
          
          .tim-typo 
            h1.title 
              span.tim-note 
                Header 1 Title
              | The Life of Material Kit
          .tim-typo 
            h2.title 
              span.tim-note 
                Header 2 Title
              | The Life of Material Kit
          .tim-typo 
            h3.title 
              span.tim-note 
                Header 3 Title
              | The Life of Material Kit
          .tim-typo 
            h4.title 
              span.tim-note 
                Header 4 Title
              | The Life of Material Kit
          .tim-typo 
            p
              span.tim-note Paragraph
              | I will be the leader of a company that ends up being worth billions of dollars, because I got the answers. I understand culture. I am the nucleus. I think that&#x2019;s a responsibility that I have, to push possibilities, to show people, this is the level that things could be at.
          .tim-typo 
            span.tim-note Quote
            .blockquote.undefined 
              p I will be the leader of a company that ends up being worth billions of dollars, because I got the answers. I understand culture. I am the nucleus. I think that&#x2019;s a responsibility that I have, to push possibilities, to show people, this is the level that things could be at.
              small  Kanye West, Musician
          .tim-typo 
            span.tim-note Muted Text
            p.text-muted  I will be the leader of a company that ends up being worth billions of dollars, because I got the answers...
          .tim-typo 
            span.tim-note Primary Text
            p.text-primary  I will be the leader of a company that ends up being worth billions of dollars, because I got the answers...
          .tim-typo 
            span.tim-note Info Text
            p.text-info  I will be the leader of a company that ends up being worth billions of dollars, because I got the answers...
          .tim-typo 
            span.tim-note Success Text
            p.text-success  I will be the leader of a company that ends up being worth billions of dollars, because I got the answers...
          .tim-typo 
            span.tim-note Warning Text
            p.text-warning  I will be the leader of a company that ends up being worth billions of dollars, because I got the answers...
          .tim-typo 
            span.tim-note Danger Text
            p.text-danger  I will be the leader of a company that ends up being worth billions of dollars, because I got the answers...
          .tim-typo 
            h2 
              span.tim-note Small Tag 
              | Header with small subtitle
              br
              small Use 'small' tag for the headers
    .space-50 
    #images 
      .title 
        h2 Images
      .md-layout 
        .md-layout-item.md-size-20.md-xsmall-size-100(:class="{ 'text-center': responsive }")
          h4 Rounded Image
          img.rounded(:src="image" alt="Rounded Image" :class="{ 'responsive-image': responsive }")
        .md-layout-item.md-size-20.md-xsmall-size-100.ml-auto(:class="{ 'text-center': responsive }")
          h4 Circle Image
          img.rounded-circle(:src="image" alt="Circle Image" :class="{ 'responsive-image': responsive }")
        .md-layout-item.md-size-20.md-xsmall-size-100.ml-auto(:class="{ 'text-center': responsive }")
          h4 Rounded Raised
          img.img-raised.rounded(:src="image" alt="Raised Image" :class="{ 'responsive-image': responsive }")
        .md-layout-item.md-size-20.md-xsmall-size-100.ml-auto(:class="{ 'text-center': responsive }")
          h4 Circle Raised
          img.img-raised.rounded-circle(:src="image" alt="Thumbnail Image" :class="{ 'responsive-image': responsive }")
  
</template>

<script>
export default {
  data() {
    return {
      image: require("@/assets/img/faces/avatar.jpg"),
      responsive: false
    };
  },
  methods: {
    onResponsiveInverted() {
      if (window.innerWidth < 600) {
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

<style lang="css </style>
