<template>
  <div class="clothrack">
    <h1>Welcome</h1>
    <div class="clothes">
      <p ref="link"><nuxt-link to="/shirts">Shirts</nuxt-link></p>
      <p><nuxt-link to="/trousers">Trousers</nuxt-link></p>
      <p><nuxt-link to="/coats">Coats</nuxt-link></p>
    </div>
  </div>
</template>

<script>
import {TimelineLite} from 'gsap'

export default {
  data() {
    return {
      tl: null
    }
  },

  mounted() {
    const tl = new TimelineLite();
    const {link} = this.$refs

    tl.to(link, 1, { rotation: 720, ease: Back.easeInOut, })

    this.tl = new TimelineLite({
      onComplete: () => tl.restart()
    })
  }
}

</script>

<style>
  /* .page-enter-active, .page-leave-active {
    transition: all .30s ease-out;
  }

  .page-enter, .page-leave-active {
    opacity: 0;
    transform: 50% 50%;
  } */

  .clothrack {
    padding: 50px;
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
  }

  .clothes {
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    width: 500px;
  }

  html, body {
    background: #9fdfbf;
    color: #000000;
    width: 100vw;
    height: 100vh;
  }

  h1 {
    width: 1000px;
    justify-content: center;
    display: flex;
  }

  a, a:visited {
    color: #ffffff;
    text-decoration: none;
  }

</style>
