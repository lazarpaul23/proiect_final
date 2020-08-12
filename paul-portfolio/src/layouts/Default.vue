<template>
  <div>
    <header class="header">
      <div class="col-xl-1"></div>
      <div class="col-xl-10 header-layout">
        <g-link class="logo" to="/">Lazar <strong>Paul</strong></g-link>
        <div class="mobile-menu">
          <button @click="toggle" class="flex mobile-btn">
            <img class="menu-icon" :class="isOpen ? 'hidden': 'block'" src="../../static/open-menu.png"/>
            <img class="menu-icon" :class="isOpen ? 'block': 'hidden'" src="../../static/close-menu.png"/>
          </button>
        </div>
        <nav class="nav desktop-menu">
          <g-link class="nav__link" to="/">Home</g-link>
          <g-link class="nav__link" to="/about/">About</g-link>
          <g-link class="nav__link" to="/curiculum-vitae/">Curiculum Vitae</g-link>
          <g-link class="nav__link" to="/contact/">Contact</g-link>
        </nav>
      </div> 
      <div>
         <ul
          class="mobile-menu block "
          :class="isOpen ? 'menu-transition-in': 'menu-transition-out'"
        > 
          <li><g-link class="nav__link" to="/">Home</g-link></li>
          <li><g-link class="nav__link" to="/about/">About</g-link></li>
          <li><g-link class="nav__link" to="/curiculum-vitae/">Curiculum Vitae</g-link></li>
          <li><g-link class="nav__link" to="/contact/">Contact</g-link></li>
        </ul>
      </div>
    </header>
    <div>
      <slot/>
    </div>
    <footer>
      <div class="footer-links">
        <div class="layout">
          <a href="https://www.facebook.com/lazar06" target="_blank"><img src="../../static/facebook.png"></a>
          <a href="https://www.linkedin.com" target="_blank"><img src="../../static/linkedin.png"></a>
          <a href="https://www.instagram.com/paul_lazar23" target="_blank"><img src="../../static/instagram.png" ></a>
        </div>
      </div>
      <div class="copyright">
        Copyright @Lazar Paul 2020. All rights reserved.
      </div>
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>

export default {
  mounted() {
    this.theme ='theme-light'
    this.$nextTick(() => {
            window.addEventListener('resize', this.onResize);
        })
  },
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
      toggle() {
        this.isOpen = !this.isOpen
      },
      onResize() {
        this.isOpen = false; 
      }
  }
}
</script>

<style>
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}

ul {
  padding-left: 0;
}

.layout {
  max-width: 760px;
  margin: auto;
}

.logo {
  font-size: 32px;  
  font-style: italic;
  color: #050b35
}

.logo:hover {
  text-decoration: none;
}

.header-layout {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
  max-width: 970px;
  width: 100%;
  margin: auto;
}

.nav__link {
  text-decoration: none;
  margin-left: 20px;
  color: #081773;
  font-weight: 500;
}

.nav__link:hover {
  text-decoration: none;
}

.footer-links {
  justify-content: space-around;
  background-color: #081773;
  margin-top: 0px;
}

.footer-links .layout{
  display: flex;
  justify-content: space-around;
  padding: 25px 0;
}

.footer-links a {
  text-decoration: none;
  color: white;
}

.footer-links img {
  width: 20px;
}

.copyright {
  display: flex;
  justify-content: center;
  background-color: #db4126;
  padding: 10px 0;
  color: white;
}

.mobile-menu {
  display: none;
}

.desktop-menu {
  display: block;
}

.mobile-btn {
  outline: none!important;
  border: 0;
  background: white;
  width: 35px;
}

@media (min-width: 768px) {
  .header-layout {
    margin-bottom: 40px;
  }
}

@media (max-width: 767px) {
  li:before {
    display: none
  }
  .mobile-menu {
    display:block;
  }

  .menu-icon {
    width: 40px
  }

  .desktop-menu {
    display: none!important;
  }
}

.menu-transition-in {
  display: block!important;
}

.menu-transition-out {
  display: none!important;
}
</style>
