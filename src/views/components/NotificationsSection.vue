<template lang="pug">
  .wrapper
    #notifications
      .alert.alert-info
        .container
          button.close(type="button" aria-hidden="true" @click="event => removeNotify(event, 'alert-info')")
            md-icon clear
          .alert-icon
            md-icon info_outline
          b INFO ALERT
          | : You've got some friends nearby, stop looking at your phone and find them...
      .alert.alert-success
        .container
          button.close(type="button" aria-hidden="true" @click="event => removeNotify(event, 'alert-success')")
            md-icon clear
          .alert-icon
            md-icon check
          b SUCCESS ALERT
          | : Yuhuuu! You've got your $11.99 album from The Weeknd
      .alert.alert-warning
        .container
          button.close(type="button" aria-hidden="true" @click="event => removeNotify(event, 'alert-warning')")
            md-icon clear
          .alert-icon
            md-icon warning
          b WARNING ALERT
          | : Hey, it looks like you still have the "copyright © 2015" in your footer. Please update it!
      .alert.alert-danger
        .container
          button.close(type="button" aria-hidden="true" @click="event => removeNotify(event, 'alert-danger')")
            md-icon clear
          .alert-icon
            md-icon info_outline
          b ERROR ALERT
          | : Damn man! You screwed up the server this time. You should find a good excuse for your Boss...
</template>

<script>
export default {
  methods: {
    removeNotify(e, notifyClass) {
      var target = e.target;
      while (target.className.indexOf(notifyClass) === -1) {
        target = target.parentNode;
      }
      return target.parentNode.removeChild(target);
    }
  }
};
</script>

<style lang="css"></style>
