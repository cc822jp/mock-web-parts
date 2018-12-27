<template>
  <figure class="logo">
    <img
      v-bind:class="{
        isShadow: isShadow,
        isAnimation: isAnimation,
        isTransition: isTransition,
        isBoxShadow: isBoxShadow,
      }"
      src="../../assets/logo.png"
    />
  </figure>
</template>

<script>
  export default {
    name: 'Logo',
    props: {
      isBoxShadow: {
        type: Boolean,
        default: false,
      },
      isShadow: {
        type: Boolean,
        default: false,
      },
      isAnimation: {
        type: Boolean,
        default: false,
      },
      isTransition: {
        type: Boolean,
        default: false,
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  figure {
    margin: 0;
    text-align: center;
  }

  img {
    max-width: 100%;
  }

  .isBoxShadow {
    box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.5);
  }

  .isShadow {
    filter: drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.5));
  }

  .isAnimation {
    animation: drop-shadow-animation 1.5s linear 0s infinite alternate;
  }

  .isTransition {
    transition: filter 0.5s ease;
  }

  @keyframes drop-shadow-animation {
    from {
      filter: drop-shadow(0px 0px 0px rgba(0, 0, 0, 0.5));
    }
    to {
      filter: drop-shadow(10px 10px 10px rgba(0, 0, 0, 0.5));
    }
  }
</style>
