<template>
  <div id="iidx" class="iidx">
      <div ref="iidx" class="mainContent">
          <div id="logo"><img src="./../assets/IIDX_Rootage_titlelogo.png"></div>
          <div id="ruleset">
              <h1>Pre-eliminary Rules</h1>
              <p>
                    Match type: Tag Team (2 players / team)<br><br>
                    Player must attends the event and registers his / her team on-site.<br><br>
                    <b>Registration will be opened on 12.00 PM closed on 14.00 or 2.00 PM sharp.</b><br> Teams which already registered, but not yet play their song beyond 14.00 or 2.00 PM, are still qualified to play until 14.30 (2.30 PM).<br><br>
                    Each team will be given 1 set of songs (2 songs), to be played during pre-eliminary round.<br><br>
                    Each player of team must play different song.<br><br>
                    Team’s EX Score will be accumulated at the end of session.<br><br>
                    2 teams with the highest accumulated score during pre-eliminary round, will advance to next round.<br><br>
                    Predefined song selection will be ranged on Level 7 - 9, up to Rootage latest update.<br><br>
              </p>
          </div>
          
        
        <div id="songlist">
            <h1>Pre-eliminary Songlists</h1>
            <div class="songContainer">
                <div class="song">
                    <img class="iidxSph" src="../assets/iidx_beingtornasky.png">
                    <div class="songDescription">
                        being torn the sky<br>Single-Play Hyper 7
                    </div>
                </div>
                <div class="song">
                    <img class="iidxSpa" src="../assets/iidx_flyabove.png">
                    <div class="songDescription">
                        Fly Above<br>Single-Play Another 8
                    </div>
                </div>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
/* eslint-disable */ 
import EventBus from '../eventBus.js'

export default {
  name: 'IIDXSection',
  data: function () {
    return {
      count: 0
    }
  },
  mounted() {
      EventBus.$on('SCROLL_TO', (ref) => {
          if (ref == 'iidx') {
            var element = this.$refs[ref];
            var position = element.getBoundingClientRect();
            var y = position.top  + window.scrollY - 75;
            window.scrollTo(0, y);
          }
        })
  }
}
</script>

<style>
    .iidx {
        /*height: 120vh;*/
        width: 100vw;
        position: relative;
        margin-bottom: 10vh;
    }
    .iidx > .mainContent {
        height: 90%;
        position: relative;
        background-color:black;
        background-image: url("./../assets/bg_iidx_section.jpg");
        background-size: cover;
    }

    .iidx > .mainContent > #logo {
        padding-top: 5vw;
    }

    .iidx > .mainContent > #logo > img{
        width: 50vw;
        max-width: 35%;
    }


    .iidx > .mainContent > #ruleset > h1 {
        text-align: center;
        height: 100%;
        color: white;
    }

    .iidx > .mainContent > #ruleset > p {
        text-align: center;
        height: 100%;
        color: white;
        list-style-type: none;
        padding: 0% 5% 0% 5%;
    }

    .iidx > .mainContent > #songlist{
        padding-top: 2vh;
        padding-bottom: 10vh;
        width: auto;
    }

    .iidx > .mainContent > #songlist > h1{
        color: white;
    }

    .iidx > .mainContent > #songlist > .songContainer {
        display: grid;
        grid-gap: 5px;
        grid-template-columns: repeat(2, 13em);
        justify-content: space-evenly;
    }
    @media screen and (max-width:600px) {
        .iidx > .mainContent > #songlist > .songContainer {
            grid-template-columns: repeat(1, 13em);
        }
    }
    
    .iidx > .mainContent > #songlist > .songContainer > .song {
        padding: 0% 5% 2.5em 5%;
    }
    .iidx > .mainContent > #songlist > .songContainer > .song > img{
        width: 10em;
        max-width: 75vw;
    }
    .iidx > .mainContent > #songlist > .songContainer > .song > .songDescription {
        color: white;
    }
    .iidxSph {
        border:7px solid #ffdc42;
    }

    .iidxSpa {
        border:7px solid #ff4949;
    }



</style>
