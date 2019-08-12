<template lang="pug">
  #material-kit
    div(:class="{ 'nav-open': NavbarStore.showNavbar }")
      router-view(name="header")
      div
        router-view
      router-view(name="footer")
</template>
