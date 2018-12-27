<template>
  <div class="container">
    <h1>box-shadow test</h1>

    <Logo :is-box-shadow="true"/>

    <hr class="hr">

    <h1>drop-shadow test</h1>

    <h2>(1) static</h2>

    <Logo :is-shadow="true"/>

    <h2>(2) animation</h2>

    <Logo :is-animation="true"/>

    <h2>(3) switch</h2>

    <div class="flex">
      <div
        v-for="(item, i) in items"
        :key="i"
        class="item"
        @click="switchItem(this, i)">
        <Logo
          :is-shadow="item"
          :is-transition="true"/>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '../components/atoms/Logo.vue'

export default {
  name: 'DropShadow',
  components: {
    Logo
  },
  data: () => {
    return {
      items: [false, false]
    }
  },
  methods: {
    switchItem: function(e, index) {
      let newItems = []
      for (let i = 0; i < this.items.length; i++) {
        newItems[i] = i === index
      }
      this.$set(this.items, 'items', newItems)
      this.items = newItems
    }
  }
}
</script>

<style scoped>
.container {
  padding: 20px;
}

.hr {
  margin: 50px 0;
}

.flex {
  display: flex;
  justify-content: center;
}

.item {
  padding: 10px;
  cursor: pointer;
}
</style>
