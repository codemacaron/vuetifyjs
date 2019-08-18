<template lang="pug">
  .wrapper
    #buttons
      .title
        h3
          | Buttons
          br
          small Pick your style
      .md-layout
        .md-layout-item.md-size-66.mx-auto
          md-button.md-primary Default
          md-button.md-primary.md-round Round
          md-button.md-primary
            md-icon favorite
            | With Icon
          md-button.md-primary.md-just-icon.md-round
            md-icon favorite
          md-button.md-primary.md-simple Simple
      .title
        h3
          small Pick your size
      .md-layout
        .md-layout-item.md-size-66.mx-auto.md-xsmall-size-100
          .vertical-center
            md-button.md-primary.md-sm Small
            md-button.md-primary Regular
            md-button.md-primary.md-lg Large
      .title
        h3
          small Pick your color
      .md-layout
        .md-layout-item.md-size-66.mx-auto
          md-button Default
          md-button.md-primary Primary
          md-button.md-info Info
          md-button.md-success Success
          md-button.md-warning Warning
          md-button.md-danger Danger
          md-button.md-rose Rose
    .space-50
    #inputs
      .title
        h3 Inputs
      .md-layout
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          md-field
            md-input(v-model="initial" placeholder="Regular")
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          md-field
            label With Floating Label
            md-input(v-model="floatingLabel" type="text")
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          md-field.md-valid
            label Success Input
            md-input(v-model="success" type="text")
            md-icon done
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          md-field.md-error
            label Error Input
            md-input(v-model="error" type="text")
            md-icon clear
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          md-field.md-form-group
            md-icon face
            md-input(v-model="withMIcon" placeholder="With Material Icons")
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          md-field.md-form-group
            i.fas.fa-users
            md-input(v-model="withFaIcon" placeholder="With Font Awesome Icons")
    .space-50
    #checkRadios
      .md-layout
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          .title
            h3 Checkboxes
          .flex-column
            md-checkbox(v-model="checkbox1") Checked
            md-checkbox(v-model="checkbox2") Unchecked
            md-checkbox(v-model="checkbox3" disabled) Disabled Checked
            md-checkbox(v-model="checkbox4" disabled) Disabled Unchecked
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          .title
            h3 Radios
          .flex-column
            md-radio(v-model="radio1" :value="true") Radio is on
            md-radio(v-model="radio1" :value="false") Radio is off
            md-radio(v-model="radio2" :value="true" disabled) Disabled Radio is on
            md-radio(v-model="radio2" :value="false" disabled) Disabled Radio is off
        .md-layout-item.md-size-25.md-xsmall-size-100.md-small-size-50.md-medium-size-25
          .title
            h3 Toggle Buttons
          .flex-column
            md-switch(v-model="switch1") Toogle is on
            md-switch(v-model="switch2") Toogle is off
    .space-70
    #progress-pagination
      .md-layout
        .md-layout-item.md-size-50.md-xsmall-size-100
          .title
            h3 Progress
          md-progress-bar.md-primaryRadio is on(:md-value="amount")
          md-progress-bar.md-infoRadio is on(:md-value="amount2")
          md-progress-bar.md-warning(md-mode="buffer" :md-value="buffer" :md-buffer="buffer")
        .md-layout-item.md-size-50.md-xsmall-size-100
          .title
            h3 Pagination
          pagination(no-arrows v-model="defaultPagination" :page-count="5")
          pagination.pagination-info(v-model="infoPagination" with-text :page-count="5")
    .space-50
    #sliders
      .md-layout
        .md-layout-item.md-size-50.md-xsmall-size-100
          .title
            h3 Sliders
          slider(v-model="sliders.simple")
          slider(v-model="sliders.rangeSlider" type="info" :connect="true")
        .md-layout-item.md-size-50.md-xsmall-size-100
          .title
            h3 Badges
          badge(type="default") Default
          badge(type="primary") Primary
          badge(type="info") Info
          badge(type="success") Success
          badge(type="warning") Warning
          badge(type="danger") Danger
          badge(type="rose") Rose
</template>

<script>
import { Pagination } from "@/components";
import { Slider } from "@/components";
import { Badge } from "@/components";

export default {
  components: {
    Pagination,
    Slider,
    Badge
  },
  data() {
    return {
      defaultPagination: 3,
      infoPagination: 3,
      initial: null,
      floatingLabel: null,
      success: null,
      error: null,
      withMIcon: null,
      withFaIcon: null,
      checkbox1: true,
      checkbox2: null,
      checkbox3: true,
      checkbox4: null,
      radio1: true,
      radio2: false,
      switch1: true,
      switch2: null,
      amount: 30,
      amount2: 60,
      buffer: 40,
      sliders: {
        simple: 40,
        rangeSlider: [20, 60]
      }
    };
  }
};
</script>

<style lang="scss" scoped>
.vertical-center {
  display: flex;
  align-items: center;
}
.flex-column {
  display: flex;
  flex-direction: column;
}
.md-checkbox,
.md-radio {
  display: flex;
  margin: 0;
  margin-bottom: 0.5rem;
}
</style>
