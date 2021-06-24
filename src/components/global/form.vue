<template>
    <form class="order">
        <span @click="hideBackdrop">X</span>
        <h2>Online order</h2>
        <p>Leave the online application form and our manager will provide a free consultation </p>
        <input type="text" placeholder="Name*">
        <input type="text" placeholder="Email*">
        <input type="text" placeholder="Phone*">
        <input type="text" placeholder="Message*">
        <button type="submit">Submit</button>
    </form>
</template>

<script>
export default {
    methods:{
        hideBackdrop(){
            this.$emit('hideBackdrop')
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.order{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem 2rem;
    height: 30rem;
    min-width: 25rem;
    
    span{
        position: absolute;
        top: 10px;
        right: 15px;
        cursor: pointer;
    }

    h2{
        font-weight: 900;
        margin-bottom: 1rem;
    }

    p{
        font-weight: 300;
        margin-bottom: 2rem;
    }

    input{
        width: 100%;
        height: 2.5rem;
        margin-bottom: 1rem;
        padding: 1rem;
        font-size: 1.1rem;
        font-weight: 300;
    }

    button{
    font-size: 1.2rem;
      font-weight: 300;
      border: none;
      background-color: $secondary-color;
      color: white;
      padding: 0.5rem 0.6rem;
      border-radius: 10px;
      cursor: pointer;
      text-transform: capitalize;
      border-bottom: 3px solid $third-color;
      justify-self: flex-end;
      margin-top: 2rem;
      width: 10rem;

      &:hover {
        background-color: $primary-color;
      }
    }
}
</style>