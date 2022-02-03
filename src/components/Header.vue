<template lang="">
  <header>
    <nav class="container">
      <a href="/">
        <img src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg" id="logo" alt="Logo WDev">
      </a>
      <img 
        src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/menu.svg" 
        id="menu-button" 
        alt="Abrir menu"
        v-on:click="openMenu"
      >
      <div id="menu-overlay" v-if="menuActive" v-on:click="closeMenu"></div>
      <div id="menu-items" :class="{active:menuActive}">
        <ul>
          <img src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg" id="menu-logo" alt="Logo WDev">
          <li><a href="/">Home</a></li>
          <li><a href="/vídeos">Vídeos</a></li>
          <li><a href="/sobre">Sobre</a></li>
          <li><a href="/contato">Contato</a></li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      menuActive: false
    }
  },
  methods: {
    openMenu: function(){
      this.menuActive = true;
    },
    closeMenu: function(){
      this.menuActive = false;
    }
  }
}
</script>

<style scoped>
  header {
    background-color: var(--color-background-nav);
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  nav {
    display: flex;
    justify-content: space-between;
    height: 60px;
    align-items: center;
  }

  #logo {
    width: 130px;
  }

  #menu-button{
    width: 30px;
  }

  #menu-overlay{
    position: fixed;
    left: 0;
    top: 0;
    width: 40%;
    height: 100vh;
    background-color: #000000;
    opacity: 0.8;
  }

  #menu-logo {
    width: 110px;
    margin-top: 30px;
    margin-bottom: 10px;
  }

  #menu-items {
    position: fixed;
    top: 0;
    right: 0;
    background-color: var(--color-background-nav);
    width: 60%;
    height: 100vh;
    display: none;
    flex-direction: column;
    align-items: center;
  }

  #menu-items.active {
    display: flex;
  }

  ul {
    list-style: none;
    text-align: center;
  }

  ul li {
    margin: 20px 0;
  }

  ul li a {
    color: var(--color-text-light);
  }

  @media (min-width: 700px) {
    #menu-button,
    #menu-logo,
    #menu-overlay {
      display: none;
    }

    #menu-items {
      display: flex;
      position: static;
      height: 60px;
      width: auto;
    }

    ul {
      display: flex;
      height: 60px;
      align-items: center;
    }

    ul li {
      margin: 0;
      margin-left: 20px;
    }
  }

</style>