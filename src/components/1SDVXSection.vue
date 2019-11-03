<template>
  <div id="sdvx" class="sdvx">
      <div ref="sdvx" class="mainContent">
            <div id="logo"><img src="./../assets/sdvx_titlelogo.png"></div>
            <div id="ruleset">
                <h1>Pre-eliminary Rules</h1>
                <p>
                        Match type: Single Player<br><br>
                        Player must attends the event and registers him/herself on-site.<br><br>
                        <b>Registration will be opened on 10.00 AM and closed on 12.00 PM sharp.</b><br> Player who already registered, but not yet play their song beyond 12.00 PM is still qualified to play until 12.30 (12.30 PM).<br><br>
                        Players will be given 1 set of songs (3 songs), to be played during pre-eliminary round.<br><br>
                        Players’ score will be accumulated at the end of session.<br><br>
                        Top 4 players with the highest accumulated score during pre-eliminary, will advance to the next round.<br><br>
                        Predefined song selection will be ranged on 15 - 16S / 17F, up to SDVX V latest update<br><br>
                </p>
            </div>
            <div id="songlist">
                <h1>Pre-eliminary Songlists</h1>
                <div class="songContainer">
                    <div class="song">
                        <img class="sdvxMxm" src="../assets/sdvx_knightofrondo.jpg">
                        <div class="songDescription">
                            Knight of Rondo<br>(ナイト・オブ・ロンド)<br>MXM 15
                        </div>
                    </div>
                    <div class="song">
                        <img class="sdvxExh" src="../assets/sdvx_paranoia.png">
                        <div class="songDescription">
                            Paranoia<br>EXH 16
                        </div>
                    </div>
                    <div class="song">
                        <img class="sdvxMxm" src="../assets/sdvx_enjoythistime.png">
                        <div class="songDescription">
                            Enjoy This Time<br>MXM 17
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
  name: 'SDVXSection',
  mounted() {
      EventBus.$on('SCROLL_TO', (ref) => {
          if (ref == 'sdvx') {
            var element = this.$refs[ref];
            var position = element.getBoundingClientRect();
            var y = position.top + window.scrollY - 75;
            window.scrollTo(0, y);
            window.scrollTo()
          }
        })
  }
}
</script>

<style>
    .sdvx {
        /*height: 120vh;*/
        width: 100vw;
        position: relative;
        margin-bottom: 10vh;
    }
    .sdvx > .mainContent {
        height: 90%;
        position: relative;
        background-color:black;
        background-image: url("./../assets/bg_sdvx_section_blurred.jpg");
        background-size: cover;
    }

    .sdvx > .mainContent > #logo {
        padding-top: 5vw;
    }

    .sdvx > .mainContent > #logo > img{
        width: 50vw;
        max-width: 35%;
    }


    .sdvx > .mainContent > #ruleset > h1 {
        text-align: center;
        height: 100%;
        color: white;
    }

    .sdvx > .mainContent > #ruleset > p {
        text-align: center;
        height: 100%;
        color: white;
        list-style-type: none;
        padding: 0% 5% 0% 5%;
    }

    .sdvx > .mainContent > #songlist{
        padding-top: 2vh;
        padding-bottom: 10vh;
        width: auto;
    }

    .sdvx > .mainContent > #songlist > h1{
        color: white;
    }

    .sdvx > .mainContent > #songlist > .songContainer {
        display: grid;
        grid-gap: 5px;
        grid-template-columns: repeat(3, 13em);
        justify-content: space-evenly;
    }
    @media screen and (max-width:600px) {
        .sdvx > .mainContent > #songlist > .songContainer {
            grid-template-columns: repeat(1, 13em);
        }
    }

    .sdvx > .mainContent > #songlist > .songContainer > .song {
        padding: 0% 5% 2.5em 5%;
    }
    .sdvx > .mainContent > #songlist > .songContainer > .song > img{
        width: 10em;
        max-width: 75vw;
    }
    .sdvx > .mainContent > #songlist > .songContainer > .song > .songDescription {
        color: white;
    }

    .sdvxMxm {
        border:7px solid #e5e5e5;
    }

    .sdvxExh{
        border:7px solid #ff4949;
    }

</style>
