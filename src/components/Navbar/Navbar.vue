<template>
  <nav :class="[scrollPosition < 70 ? 'nav navDown' : 'nav']">
    <div class="nav-logo">
      <a href="#header" v-smooth-scroll
        ><img src="../../assets/img/logo-black.png" alt=""
      /></a>
    </div>
    <ul class="nav-links">
      <li id="home">
        <a href="#header" v-smooth-scroll
          >Home
          <svg class="nav--icon--arrow">
            <use
              xlink:href="../../assets/sprite.svg#icon-keyboard_arrow_down"
            ></use>
          </svg>
        </a>

        <ul>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
        </ul>
      </li>

      <li><a href="#services" v-smooth-scroll>service</a></li>
      <li><a href="#about" v-smooth-scroll>about us</a></li>
      <li><a href="#" v-smooth-scroll>discount</a></li>
      <li><a href="#reviews" v-smooth-scroll>reviews</a></li>
      <li><a href="#price" v-smooth-scroll>price</a></li>
      <li id="contact">
        <a href="#contact" v-smooth-scroll
          >contact
          <svg class="nav--icon--arrow">
            <use
              xlink:href="../../assets/sprite.svg#icon-keyboard_arrow_down"
            ></use></svg
        ></a>
        <ul>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
          <li>Sub Menu link</li>
        </ul>
      </li>
    </ul>
    <div class="nav-icons">
      <div class="icon--container">
        <span>0</span>
        <svg class="nav--icon" id="basket">
          <span>eapgaegp</span>
          <use xlink:href="../../assets/sprite.svg#icon-shopping-basket"></use>
        </svg>
      </div>

      <div class="icon--container">
        <svg class="nav--icon">
          <use xlink:href="../../assets/sprite.svg#icon-search"></use>
        </svg>
      </div>
    </div>
    <div
      class="menu--icon--container"
      @click="showMobileMenu = !showMobileMenu"
    >
      <svg class="menu--icon">
        <use xlink:href="../../assets/sprite.svg#icon-menu"></use>
      </svg>
    </div>

    <mobile-nav
      :showMobileMenu="showMobileMenu"
      @closeNav="showMobileMenu = false"
    />
  </nav>
</template>

<script>
import mobileNav from "./mobileNav.vue";
export default {
  data() {
    return {
      showMobileMenu: false,
      scrollPosition: 0,
    };
  },
  components: {
    mobileNav,
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.nav {
  width: 100%;
  height: 4.7rem;
  background-color: white;

  display: flex;
  justify-content: space-around;
  align-items: center;

  padding: 0 5rem;

  position: fixed;
  top: 0;
  left: 0;

  z-index: 110;


  @media only screen and (max-width: 988px) {
    justify-content: space-between;
    padding: 0 0.5rem;
  }

  &-logo {
    width: 16rem;
    padding: 1rem 1.5rem;

    @media only screen and (max-width: 988px) {
      width: 6rem;
    }

    img {
      width: 100%;
      min-width: 10rem;
      cursor: pointer;
    }
  }

  &-links {
    list-style: none;
    display: flex;
    height: 100%;

    @media only screen and (max-width: 988px) {
      display: none;
    }

    li {
      height: 100%;
      width: 6rem;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      position: relative;

      &::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 0rem;
        height: 0.2rem;
        transition: all 0.3s;
        background-color: $primary-color;
      }

      &:hover {
        &::before {
          width: 100%;
        }
      }

      a {
        text-decoration: none;
        text-transform: uppercase;
        color: black;
        font-weight: 300;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }

    li#home ul,
    li#contact ul {
      position: absolute;
      width: 10rem;
      left: 0;
      top: 4.7rem;
      display: none;
      flex-direction: column;
      align-items: center;
      margin: 0;
      padding: 0;
      background-color: #fff;
      box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
      transition: all 0.3s;

      li {
        color: $primary-color;
        padding: 10px 14px;
        text-decoration: none;
        display: block;
        cursor: pointer;
        font-size: 1rem;
        font-weight: 400;
        transition: all 0.3s;
        width: 100%;
        display: flex;
        justify-content: center;

        &:hover {
          background-color: $primary-color;
          color: #fff;
        }
      }
    }

    li#home:hover ul,
    li#contact:hover ul{
      display: flex;
    }
  }

  &-icons {
    display: flex;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-around;
    min-width: 5rem;

    @media only screen and (max-width: 988px) {
      display: none;
    }

    .icon--container {
      position: relative;

      span {
        position: absolute;
        top: -5px;
        right: -4px;
        font-size: 12px;
        background: #2194e0;
        width: 17px;
        height: 17px;
        border-radius: 50%;
        color: #fff;
        font-weight: 700;
        z-index: 1;
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }

    .nav--icon {
      width: 1.2rem;
      height: 1.2rem;
      fill: rgb(41, 41, 41);
      cursor: pointer;
      transition: all .2s;

      &:hover{
        width: 1.4rem;
        height: 1.4rem;
      }
    }

    .nav--icon#basket {
      position: relative;
    }
  }

  .menu--icon {
    width: 2rem;
    height: 2rem;
    fill: rgb(41, 41, 41);
    cursor: pointer;

    @media only screen and (min-width: 988px) {
      display: none;
    }
  }
}

.nav.navDown {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  top: 4rem;
  width: 80%;
  padding: 0 1rem;

  @media only screen and (max-width: 1185px) {
    position: fixed;
    top: 0;
    left: 0;
    transform: none;
    width: 100%;
  }
}

.nav--icon--arrow {
  width: 1rem;
  height: 1rem;
}


</style>