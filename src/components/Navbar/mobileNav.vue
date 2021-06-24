<template>
  <div :class="[showMobileMenu ? 'mobile--nav open' : 'mobile--nav']">
    <ul class="mobile--nav-links">
      <li id="subMenu">
        <a href="#" @click="showSubMenu('home')"
          >Home
          <svg class="nav--icon--arrow">
            <use
              xlink:href="../../assets/sprite.svg#icon-keyboard_arrow_down"
            ></use></svg
        ></a>
        <transition name="expand">
          <ul v-if="showHomeSub">
            <li><a href="#">Sub Link</a></li>
            <li><a href="#">Sub Link</a></li>
            <li><a href="#">Sub Link</a></li>
            <li><a href="#">Sub Link</a></li>
          </ul>
        </transition>
      </li>
      <li>
        <a href="#services" v-smooth-scroll @click="$emit('closeNav')"
          >service</a
        >
      </li>
      <li>
        <a href="#about" v-smooth-scroll @click="$emit('closeNav')">about us</a>
      </li>
      <li>
        <a href="#" v-smooth-scroll @click="$emit('closeNav')">discount</a>
      </li>
      <li>
        <a href="#reviews" v-smooth-scroll @click="$emit('closeNav')"
          >reviews</a
        >
      </li>
      <li>
        <a href="#price" v-smooth-scroll @click="$emit('closeNav')">price</a>
      </li>
      <li id="subMenu">
        <a href="#" @click="showSubMenu('contact')"
          >contact
          <svg class="nav--icon--arrow">
            <use
              xlink:href="../../assets/sprite.svg#icon-keyboard_arrow_down"
            ></use></svg
        ></a>
        <transition name="expand">
          <ul v-if="showContactSub">
            <li><a href="#">Sub Link</a></li>
            <li><a href="#">Sub Link</a></li>
            <li><a href="#">Sub Link</a></li>
          </ul>
        </transition>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    showMobileMenu: Boolean,
  },
  data() {
    return {
      showHomeSub: false,
      showContactSub: false,
    };
  },
  methods: {
    showSubMenu(menu) {
      if (menu == "home") {
        this.showHomeSub = !this.showHomeSub;
        this.showContactSub = false;
      } else {
        this.showContactSub = !this.showContactSub;
        this.showHomeSub = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

// Mobile nav
.mobile--nav {
  position: fixed;
  left: 0;
  width: 100%;
  top: -100%;
  opacity: 0;
  height: 100%;
  background-color: $primary-color;
  transition: all 0.2s ease-in-out;
  z-index: 100;

  @media only screen and (min-width: 988px) {
    display: none;
  }

  &-links {
    //height: 100%;
    //width: 100%;
    display: flex;
    padding: 2rem 0;
    //align-items: center;
    justify-content: center;
    flex-direction: column;

    //list-style: none;


    & > * {
      margin-bottom: 2rem;
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    li#subMenu {
      position: relative;

      ul {
        list-style: none;
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding: 1rem 1rem;
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        border-bottom: 1px solid rgba(255, 255, 255, 0.432);
        background-color: $secondary-color;
        margin-top: .5rem;

        li {
          margin-bottom: 1rem;
        }
      }
    }

    a {
      text-decoration: none;
      text-transform: uppercase;
      color: white;
      font-size: 1rem;
    }
  }
}

.mobile--nav.open {
  top: 4.7rem;
  opacity: 1;
}

.nav--icon--arrow {
  width: 1rem;
  height: 1rem;
  fill: white;
  position: absolute;
  top: 3px;
}

.expand-enter-active,
.expand-leave-active {
  transition: opacity 0.3s;
}
.expand-enter,
.expand-leave-to {
  opacity: 0;
}
</style>