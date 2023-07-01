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
              <router-link 
                to="/" 
                @click="setNavOpen"
                :style="{top: state.navOpen ? '0' : '120px', transitionDelay: state.navOpen ? '.8s' : '0s'}"
                >Home</router-link>
              <div class="nav-item-wrapper"></div>
            </li>
            <li class="nav-item">
              <router-link 
                to="/projets" 
                @click="setNavOpen"
                :style="{top: state.navOpen ? '0' : '120px', transitionDelay: state.navOpen ? '.9s' : '0s'}"
                >Projects</router-link>
              <div class="nav-item-wrapper"></div>
            </li>
            <li class="nav-item">
              <router-link 
                to="/about" 
                @click="setNavOpen"
                :style="{top: state.navOpen ? '0' : '120px', transitionDelay: state.navOpen ? '1s' : '0s'}"
                >About</router-link>
              <div class="nav-item-wrapper"></div>
            </li>
            <li class="nav-item">
              <router-link 
                to="/" 
                @click="setNavOpen"
                :style="{top: state.navOpen ? '0' : '120px', transitionDelay: state.navOpen ? '1.1s' : '0s'}"
                >Contact</router-link>
              <div class="nav-item-wrapper"></div>
            </li>
          </ul>
          <div class="nav-footer">
            <div 
              class="location"
              :style="{
                bottom: state.navOpen ? '0' : '-20px',
                opacity: state.navOpen ? '1' : '0',
                transitionDelay: state.navOpen ? '1.2s' : '0s'
                }">
              <span>Paris, IDF</span>
            </div>
            <div class="nav-social-media">
              <ul>
                <li>
                  <router-link 
                    to="/"
                    :style="{
                      bottom: state.navOpen ? '0' : '-20px',
                      opacity: state.navOpen ? '1' : '0',
                      transitionDelay: state.navOpen ? '1.3s' : '0s'
                      }">Twitter</router-link>
                </li>
                <li>
                  <router-link 
                    to="/"
                    :style="{
                    bottom: state.navOpen ? '0' : '-20px',
                    opacity: state.navOpen ? '1' : '0',
                    transitionDelay: state.navOpen ? '1.4s' : '0s'
                    }">Github</router-link>
                </li>
              </ul>
            </div>
          </div>
        </div>
    </div>
  </div>
</template>