<template>
  <div id="ddr" class="ddr">
      <div ref="ddr" class="mainContent">
          <div id="logo"><img src="./../assets/ddr_titlelogo.png"></div>
          <div id="ruleset">
              <h1>Pre-eliminary Rules</h1>
              <p>
                    Match type: Team Battle (3 players / team)<br><br>
                    Player must attends the event and registers his / her team on-site.<br><br>
                    <b>Registration will be opened on 12.00 PM and closed on 14.00 or 2.00 PM sharp.</b><br> Teams which already registered, but not yet play their song beyond 14.00 or 2.00 PM, are still qualified to play until 14.30 (2.30 PM).<br><br>
                    Each team will be given 1 set of songs (3 songs), to be played during pre-eliminary round.<br><br>
                    Each player of team must play different song.<br><br>
                    Team’s EX Score will accumulated at the end of play.<br><br>
                    2 teams with the highest accumulated score during pre-eliminary, will advance to next round.<br><br>
                    Predefined song selection will be ranged on Level 8 - 12, up to DDR A Asia latest update.<br><br>
              </p>
          </div>
        <div id="songlist">
            <h1>Pre-eliminary Songlists</h1>
            <div class="songContainer">
                <div class="song">
                    <img class="ddrExp" src="../assets/ddr_astupidbarber.png">
                    <div class="songDescription">
                        A Stupid Barber<br>Expert Single-Play 9
                    </div>
                </div>
                <div class="song">
                    <img class="ddrExp" src="../assets/ddr_dazzlindarlin.png">
                    <div class="songDescription">
                        Dazzlin Darlin<br>Expert Single-Play 11
                    </div>
                </div>
                <div class="song">
                    <img class="ddrExp" src="../assets/ddr_theoryofeternity.png">
                    <div class="songDescription">
                        Theory of Eternity<br>Expert Single-Play 12
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
  name: 'DDRSection',
  data: function () {
    return {
      count: 0
    }
  },
  mounted() {
      EventBus.$on('SCROLL_TO', (ref) => {
          if (ref == 'ddr') {
            var element = this.$refs[ref];
            var position = element.getBoundingClientRect();
            var y = position.top + window.scrollY - 75;
            window.scrollTo(0, y);
          }
        })
  }
}
</script>

<style>
    .ddr {
        /*height: 120vh;*/
        width: 100vw;
        position: relative;
        margin-bottom: 10vh;
    }
    .ddr > .mainContent {
        height: 90%;
        position: relative;
        background-color:black;
        background-image: url("./../assets/bg_ddr_section.jpg");
        background-size: cover;
    }

    .ddr > .mainContent > #logo {
        padding-top: 5vw;
    }

    .ddr > .mainContent > #logo > img{
        width: 50vw;
        max-width: 35%;
    }


    .ddr > .mainContent > #ruleset > h1 {
        text-align: center;
        height: 100%;
        color: white;
    }

    .ddr > .mainContent > #ruleset > p {
        text-align: center;
        height: 100%;
        color: white;
        list-style-type: none;
        padding: 0% 5% 0% 5%;
    }

    .ddr > .mainContent > #songlist{
        padding-top: 2vh;
        padding-bottom: 10vh;
        width: auto;
    }

    .ddr > .mainContent > #songlist > h1{
        color: white;
    }

    .ddr > .mainContent > #songlist > .songContainer {
        display: grid;
        grid-gap: 5px;
        grid-template-columns: repeat(3, 13em);
        justify-content: space-evenly;
    }
    @media screen and (max-width:600px) {
        .ddr > .mainContent > #songlist > .songContainer {
            grid-template-columns: repeat(1, 13em);
        }
    }
    
    .ddr > .mainContent > #songlist > .songContainer > .song {
        padding: 0% 5% 2.5em 5%;
    }
    .ddr > .mainContent > #songlist > .songContainer > .song > img{
        width: 10em;
        max-width: 75vw;
    }
    .ddr > .mainContent > #songlist > .songContainer > .song > .songDescription {
        color: white;
    }
    .ddrExp {
        border:7px solid #209b32;
    }

</style>
