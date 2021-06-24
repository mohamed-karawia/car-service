<template>
  <div class="content--part" :style="`background-color: ${content.color};`">
    <svg class="content--part__icon">
      <use
        :xlink:href="require('@/assets/sprite.svg') + `#${content.icon}`"
      ></use>
    </svg>
    <div class="content--part__detail">
      <svg class="arrow">
        <use
          xlink:href="../../assets/sprite.svg#icon-keyboard_arrow_right"
        ></use>
      </svg>
      <p>{{ content.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    content: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.content--part {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 11rem;

  flex: 1;

  @media only screen and (max-width: 720px) {
    padding: 2rem 0;
  }

  &__icon {
    fill: white;
    width: 2.5rem;
    height: 2.5rem;
    cursor: pointer;
    transition: all .2s;

          &:hover{
        width: 2.7rem;
        height: 2.7rem;
      }
  }

  &__detail {
    display: flex;
    align-items: center;
    margin-top: 1.5rem;

    p {
      color: white;
      text-transform: uppercase;
      font-weight: 900;
    }

    .arrow {
      fill: white;
      width: 1rem;
      height: 1rem;
      font-weight: 900;
    }
  }
}


</style>