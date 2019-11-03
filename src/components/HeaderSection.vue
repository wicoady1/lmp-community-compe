<template>
  <div id="header" class="header">
      <div class="trigger"> </div>
      <div class="content">
          <div id="backgroundColor"></div>
          <div id="menu">
              <div class="game"><img src="./../assets/sdvx_titlelogo.png" @click="scrollMeTo('sdvx')"></div>
              <div class="game"><img src="./../assets/IIDX_Rootage_titlelogo.png" @click="scrollMeTo('iidx')"></div>
              <div class="game"><img src="./../assets/ddr_titlelogo.png" @click="scrollMeTo('ddr')"></div>
          </div>
      </div>
  </div>
</template>

<script>
/* eslint-disable */ 
import { TweenMax, Elastic } from 'gsap'
import 'gsap/ScrollToPlugin'
import EventBus from '../eventBus.js'

export default {
  name: 'HeaderSection',
  data: function () {
    return {
      count: 0
    }
  },
  methods: {
    scrollMeTo(refName) {
            EventBus.$emit('SCROLL_TO', refName)
        }
    }
}
</script>

<style>
    .header{
        position: relative;
    }
    .header > .content > #backgroundColor {
        width: 100%;
        height: 75px;
        position: fixed;
        background-color: white;
        z-index: -99999;
        opacity: 1;
    }
    .header > .content > #logo > h1{
        margin: auto;
        vertical-align: middle;
        display: table-cell;
        padding-left: 2vw;
    }
    .header > .content {
        width: 100vw;
        position: fixed;
        z-index: 99999;
        height: 75px;
        margin: auto;
    } 
    .header > .content > #logo {
        opacity: 0;
        height: 100%;
        display: table;
        /*padding: 25px 25px 25px 25px;*/
        float:left;
    }
    .header > .content > #menu {
        padding: 7px 5px 7px 5px;
        width: 50%;
        margin: auto;
        display: table
    }
    .header > .content > #menu > .game {
        display: table-cell;
        padding-left: 1vw;
        padding-right: 1vw;
    }
    .game > img {
        height: auto;
        max-height: 55px;
        max-width: 30vw;
    }

</style>
