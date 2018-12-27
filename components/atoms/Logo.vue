<template>
  <figure class="logo">
    <img
      :class="{
        isDsShadow: isDsShadow,
        isBsShadow: isBsShadow,
        isDsAnimation: isDsAnimation,
        isBsAnimation: isBsAnimation,
        isDsTransition: isDsTransition,
        isBsTransition: isBsTransition,
      }"
      src="../../assets/logo.png"
    >
  </figure>
</template>

<script>
export default {
  name: 'Logo',
  props: {
    isDsShadow: {
      type: Boolean,
      default: false
    },
    isBsShadow: {
      type: Boolean,
      default: false
    },
    isDsAnimation: {
      type: Boolean,
      default: false
    },
    isBsAnimation: {
      type: Boolean,
      default: false
    },
    isDsTransition: {
      type: Boolean,
      default: false
    },
    isBsTransition: {
      type: Boolean,
      default: false
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

.isDsShadow {
  filter: drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.5));
}

.isBsShadow {
  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.5);
}

.isDsAnimation {
  animation: drop-shadow-animation 1.5s linear 0s infinite alternate;
}

.isBsAnimation {
  animation: box-shadow-animation 1.5s linear 0s infinite alternate;
}

.isDsTransition {
  transition: filter 0.5s ease;
}

.isBsTransition {
  transition: box-shadow 0.5s ease;
}

@keyframes drop-shadow-animation {
  from {
    filter: drop-shadow(0px 0px 0px rgba(0, 0, 0, 0.5));
  }
  to {
    filter: drop-shadow(10px 10px 10px rgba(0, 0, 0, 0.5));
  }
}

@keyframes box-shadow-animation {
  from {
    box-shadow: 0 0 0 rgba(0, 0, 0, 0.5);
  }
  to {
    box-shadow: 10px 10px 10px rgba(0, 0, 0, 0.5);
  }
}
</style>
