<template>
  <div class="c-main-container container is-widescreen">
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" />
      </transition>
    </router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang="scss">
@import 'assets/vendor';
@import 'assets/common';

html, body {
  height: 100%;
  overflow: auto;
}
body {
  background-image: url('/money-dark-optimized.png');
  background-size: cover;
}
.c-main-container {
  padding: 20px;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s
}
.fade-enter-from, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0
}
</style>
