<template>
  <div id="app">
    <transition enter-active-class="animated pulse">
      <keep-alive exclude="Detail">
        <router-view/>
      </keep-alive>
    </transition>
  </div>
</template>

<style lang="stylus">
</style>
