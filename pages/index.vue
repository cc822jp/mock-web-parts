<template>
  <section class="container">
    <logo/>
  </section>
</template>

<script>
import Logo from '../components/atoms/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
