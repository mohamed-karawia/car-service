<template>
  <div class="Expander">
    <div
      class="Expander__trigger"
      @click="open = !open"
      :class="open ? 'active' : 'beforeBorder'"
    >
      <svg
        class="Expander__trigger-Icon"
        :class="{ open: open }"
        width="40"
        height="12"
        stroke="cornflowerblue"
      >
        <polyline
          points="12,2 20,10 28,2"
          stroke-width="3"
          fill="none"
        ></polyline>
      </svg>
      {{ question.question }}
    </div>
    <transition name="bottomToTop">
      <div class="Expander__body" v-show="open">
        <p>{{ question.answer }}</p>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      open: false,
    };
  },
  props:{
      question: Object
  }
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.Expander{
    //border: 1px solid black;
    margin-bottom: 1rem;
}

.beforeBorder {
  position: relative;
  &:before {
    transition: opacity 0.1s linear, transform 0.5s ease-in-out;
    position: absolute;
    border-bottom: 1px solid currentColor;
    content: "";
    width: 100%;
    left: 0;
    bottom: -1px;
  }
  &:not(:hover)::before {
    transform: scaleX(0);
    opacity: 0;
  }
}
.Accordion {
  background: #fff;
  box-shadow: 0 1px 12px 1px rgba(0, 0, 0, 0.25);
  overflow: hidden;
}
.Expander__trigger {
  cursor: pointer;
  padding: 0.7rem 0.5rem;
  border-bottom: 1px solid #efefef;
  font-size: 1.2rem;
  font-weight: 300;
  height: 4rem;
  display: flex;
  align-items: center;
  background-color: $gray;
  &:hover {
    color: #477dca;
  }
  &.active {
    border-bottom-color: #477dca;
  }

  &-Icon {
    transition: transform 0.2s cubic-bezier(0.23, 1, 0.32, 1);
    &.open {
      stroke: #ff6347;
      transform: rotate(180deg);
    }
  }
}

.Expander__body {
  padding: 1rem 1.5rem;
  background: #ffff;
}

.bottomToTop-enter-active {
  animation: bottomToTop 0.3s forwards;
}
.bottomToTop-leave-active {
  animation: bottomToTop 0.3s reverse;
}

@keyframes bottomToTop {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  100% {
    transform: translateY(0);
  }
}
</style>