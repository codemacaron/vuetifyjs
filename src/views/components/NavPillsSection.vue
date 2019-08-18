<template lang="pug">
  .wrapper
    #navigation-pills
      .title
        h3 Navigation Pills
      .title
        h3
          small With Icons
      .md-layout
        .md-layout-item.md-size-50.md-small-size-100
          tabs(:tab-name="['Dashboard', 'Schedule', 'Tasks']" :tab-icon="['dashboard', 'schedule', 'list']" plain nav-pills-icons color-button="primary")
            template(slot="tab-pane-1")
              | Collaboratively administrate empowered markets via plug-and-play networks. Dynamically procrastinate B2C users after installed base benefits.
              br
              br
              | Dramatically visualize customer directed convergence without revolutionary ROI.
            template(slot="tab-pane-2")
              | Efficiently unleash cross-media information without cross-media value. Quickly maximize timely deliverables for real-time schemas.
              br
              br
              | Dramatically maintain clicks-and-mortar solutions without functional solutions.
            template(slot="tab-pane-3")
              | Completely synergize resource taxing relationships via premier niche markets. Professionally cultivate one-to-one customer service with robust ideas.
              br
              br
              | Dynamically innovate resource-leveling customer service for state of the art customer service.
        .md-layout-item.md-size-50.md-small-size-100
          tabs(:tab-name="['Dashboard', 'Schedule']" :tab-icon="['dashboard', 'schedule']" plain flex-column nav-pills-icons color-button="primary")
            template(slot="tab-pane-1")
              | Collaboratively administrate empowered markets via plug-and-play networks. Dynamically procrastinate B2C users after installed base benefits.
              br
              br
              | Dramatically visualize customer directed convergence without revolutionary ROI.
            template(slot="tab-pane-2")
              | Efficiently unleash cross-media information without cross-media value. Quickly maximize timely deliverables for real-time schemas.
              br
              br
              Dramatically maintain clicks-and-mortar solutions without functional solutions.
</template>

<script>
import { Tabs } from "@/components";

export default {
  components: {
    Tabs
  }
};
</script>

<style lang="css"></style>
