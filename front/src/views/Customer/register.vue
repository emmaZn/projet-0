<template>
  <div class="home">
    <img class="logo" src="../../assets/logoBlanc.svg" alt="icone de feuille de canabis kawaii" />
    <router-link :to="{ name: 'Home' }">
      <button color="secondary" class="rounded button-runner">Déjà <br class="br"> inscrit</button>
    </router-link>
    <h1 class="title" data-text="Miguel la petite feuille de canabis !">
      Just Smoke It
    </h1>
    <v-form-inscription-client></v-form-inscription-client>
    <!-- credits : GoodKatz -->
    <svg class="waves" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
      viewBox="0 24 150 28" preserveAspectRatio="none" shape-rendering="auto">
      <defs>
        <path id="gentle-wave" d="M-160 44c30 0 58-18 88-18s 58 18 88 18 58-18 88-18 58 18 88 18 v44h-352z" />
      </defs>
      <g class="parallax">
        <use xlink:href="#gentle-wave" x="48" y="0" fill="rgba(255, 170, 170, 0.5)" />
        <use xlink:href="#gentle-wave" x="48" y="3" fill="rgba(255, 255, 255, 1)" />
        <use xlink:href="#gentle-wave" x="48" y="5" fill="rgba(255, 170, 170, 0.7)" />
        <use xlink:href="#gentle-wave" x="48" y="7" fill="rgba(255, 170, 170, 1)" />
      </g>
    </svg>
  </div>
</template>

<script>
  import VFormInscriptionClient from "@/components/Customer/VFormInscriptionClient.vue";

  export default {
    components: {
      VFormInscriptionClient,
    },
  };
</script>

<style lang="scss" scoped>
  $color1-btn: #ffaaaa;

  .br {
    display: none;
  }
  .home {
    height: 100%;
    padding: 0px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background: linear-gradient(135deg, #8ee2cf 0%, #6fce91 100%);

    .rounded {
      font-family: Rubik, sans-serif;
      font-size: 1.5em;
      border: solid 2px rgba(111, 206, 145, 1);
      color: white;
      width: 10em;
      border-radius: 50px !important;
      position: absolute;
      top: 20px;
      right: 20px;
      height: 2em;
      outline: none;
      transition: 300ms;
      background-color: #ffaaaa;

      &:hover {
        color: rgba(111, 206, 145, 1);
        background-color: white;
      }
    }
  }

  .title {
    font-weight: 900;
    font-size: 5vmin !important;
    font-family: "Poppins", sans-serif !important;
    color: white;
    margin-top: 3vh;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.4);
  }

  //logo animation

  @keyframes popLogo {
    0% {
      transform: scale(0);
    }

    25% {
      transform: scale(0);
    }

    50% {
      transform: scale(1.2);
    }

    70% {
      transform: scale(1);
    }

    85% {
      transform: scale(1.1);
    }

    100% {
      transform: scale(1);
    }
  }

  .logo {
    height: 10em;
    margin-top: 3vh;
    animation: 1s ease-in-out 0s 1 popLogo;
  }

  // Waves and waves animation, credits : GoodKatz (https://codepen.io/goodkatz/details/LYPGxQz)
  .waves {
    margin: 0px;
    position: absolute;
    bottom: 0px;
    height: 12vh;
    width: 100%;
  }

  .parallax>use {
    animation: move-forever 25s cubic-bezier(0.55, 0.5, 0.45, 0.5) infinite;
  }

  .parallax>use:nth-child(1) {
    animation-delay: -2s;
    animation-duration: 25s;
  }

  .parallax>use:nth-child(2) {
    animation-delay: -3s;
    animation-duration: 20s;
  }

  .parallax>use:nth-child(3) {
    animation-delay: -4s;
    animation-duration: 15s;
  }

  .parallax>use:nth-child(4) {
    animation-delay: -5s;
    animation-duration: 12s;
  }

  @keyframes move-forever {
    0% {
      transform: translate3d(-90px, 0, 0);
    }

    100% {
      transform: translate3d(85px, 0, 0);
    }
  }

  @media screen and (max-width:700px) {
    .container {
      padding: 0;
      margin-left: 6vw;
      margin-right: 6vw;
      width: 92vw;
    }
    .br {
      display: block;
    }
    .logo {
      height: auto !important;
      width: 75px;
      margin-top: 1% !important
    }
    .button-runner {
      height: 7vh !important;
      width: 26vw !important;
      margin-right: 1vw!important;
    }
    .rounded {
      font-size: 12px !important;
      top: 20px;
      margin-right: -33px;
      height: 2vh;
      width: 1vw;
    }
    .waves {
      display: none;
    }
    .title {
      font-weight: 900;
      font-size: 40px !important;
      margin-bottom: 1vh;
    }
  }
</style>