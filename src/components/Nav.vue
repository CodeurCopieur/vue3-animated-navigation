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
        <div 
          class="nav-overlay" 
          :style="{top: state.navOpen ? '0' : '-100%', transitionDelay: state.navOpen ? '0s' : '0s'}">
          <ul class="nav-links">
            <li class="nav-item">
              <router-link to="/">Home</router-link>
              <div class="nav-item-wrapper"></div>
            </li>
            <li class="nav-item">
              <router-link to="/">Project</router-link>
              <div class="nav-item-wrapper"></div>
            </li>
            <li class="nav-item">
              <router-link to="/">About</router-link>
              <div class="nav-item-wrapper"></div>
            </li>
            <li class="nav-item">
              <router-link to="/">Contact</router-link>
              <div class="nav-item-wrapper"></div>
            </li>
          </ul>
          <div class="nav-footer">
            <div class="location">
              <span>Paris, IDF</span>
            </div>
            <div class="nav-social-media">
              <ul>
                <li>
                  <router-link to="/">Twitter</router-link>
                </li>
                <li>
                  <router-link to="/">Github</router-link>
                </li>
              </ul>
            </div>
          </div>
        </div>
    </div>
  </div>
</template>