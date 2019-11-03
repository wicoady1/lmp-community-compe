<template>
  <div id="intro" class="intro">
      <div class="mainContent">
          <div id="leftContainer"><h1>BEMANI Community Event</h1></div>
          <div id="separator"></div>
          <div id="rightContainer">
                  <h3>
                    <b>Venue:</b><br>
                    Lippo Mall Puri - LG - Takeshita Street<br>
                    (<a href="https://www.google.com/maps/place/Lippo+Mall+Puri/@-6.1878527,106.7365294,17z/data=!3m1!4b1!4m5!3m4!1s0x2e69f76e37136e23:0x41cca4768f8bf65b!8m2!3d-6.187858!4d106.7387181">
                    Location by Google Maps
                    </a>)<br><br>
                    <b>Date:</b><br> Sunday, March 28th, 2019<br><br>
                    <b>Time:</b><br> 10.00 AM - 07.00 PM
                  </h3>
          </div>
      </div>
      <div class="lowerEmpty"></div>
  </div>
</template>

<script>
/* eslint-disable */ 
export default {
  name: 'IntroSection',
  data: function () {
    return {
      count: 0
    }
  }
}
</script>

<style>
    .intro {
        height: 100vh;
        width: 100vw;
        position: relative;
    }
    .lowerEmpty {
        height: 20%;
        position: relative;
    }
    .mainContent {
        height: 80%;
        width: 90%;
        padding: 75px 5% 0% 5%;
        position: relative;
        background-color:black;
        background-image: url("./../assets/bg_lmp.jpeg");
        background-size: cover;
    }

    .mainContent > #leftContainer {
        width: 40%;
        height: 100%;
        float: left;
        display: table;
    }
    .mainContent > #leftContainer > h1 {
        display: table-cell;
        text-align: right;
        vertical-align: middle;
        height: 100%;
        color: white;
    }
    @media screen and (max-width:500px) {
        .mainContent > #leftContainer > h1 {
            font-size: 1.3em;
        }
    }

    .mainContent > #separator {
        width: 10%;
        height: 100%;
        float: left;
        background-image: url("./../assets/line_separator.png");
        background-repeat: no-repeat;
        background-position: center;
    }

    .mainContent > #separator > img {
        display:block;
        margin:auto;
    }

    .mainContent > #rightContainer {
        width: 40%;
        height: 100%;
        display: table;
    }
    .mainContent > #rightContainer > h3 > a {
        text-decoration: underline;
        color: white;
    }
    
    .mainContent > #rightContainer > h3 {
        display: table-cell;
        text-align: left;
        vertical-align: middle;
        height: 100%;
        color: white;
    }
    @media screen and (max-width:500px) {
        .mainContent > #rightContainer > h3 {
            font-size: 1em;
        }
    }

    @media screen and (max-width:400px) {
        .mainContent > #rightContainer > h3 {
            font-size: 0.8em;
        }
    }
</style>
