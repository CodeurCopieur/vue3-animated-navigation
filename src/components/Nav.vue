<script setup>
  import {reactive} from 'vue'

  const state = reactive({
    navOpen: false
  });

  const setNavOpen = () => {
    state.navOpen = !state.navOpen
  };

</script>

<template>
  <div class="nav">
    <div class="nav-container">
        <div class="navbar">
          <div class="logo">CodeurCopieur</div>
          <div class="menu-toggle" @click="setNavOpen">
            <div class="hamBox" :class="{'hamBoxOpen' : state.navOpen}">
              <span class="lineTop" :class="{'spin' : state.navOpen}"></span>
              <span class="lineBottom" :class="{'spin' : state.navOpen}"></span>
            </div>
          </div>
        </div>
        <div class="nav-overlay" :style="{top: state.navOpen ? '0' : '-100%', transitionDelay: state.navOpen ? '0s' : '0s'}"></div>
    </div>
  </div>
</template>