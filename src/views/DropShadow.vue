<template>
  <div>
    <h1>box-shadow test</h1>

    <Logo v-bind:is-box-shadow="true"/>

    <hr class="hr">

    <h1>drop-shadow test</h1>

    <h2>(1) static</h2>

    <Logo v-bind:is-shadow="true"/>

    <h2>(2) animation</h2>

    <Logo v-bind:is-animation="true"/>

    <h2>(3) switch</h2>

    <div class="flex">
      <div v-for="(item, i) in items" class="item" v-on:click="switchItem(this, i)">
        <Logo v-bind:is-shadow="item" v-bind:is-transition="true" />
      </div>
    </div>
  </div>
</template>

<script>
  import Logo from '../components/atoms/Logo.vue'

  export default {
    name: 'home',
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
        let newItems = [];

        for (let i = 0; i < this.items.length; i++) {
          newItems[i] = (i === index);
        }

        this.$set(this.items, 'items', newItems);
        this.items = newItems;
      }
    }
  }
</script>

<style scoped>
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
