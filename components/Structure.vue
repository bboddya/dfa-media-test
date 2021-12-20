<template>
<div class="container_body">
  <Nav :isActive="this.burgerValue"/>

  <div class="right">
    <Header @toggleBurger="toggleBurger"/>
    
    <section class="container container_blue">
        <h1 class="title">Моя структура</h1>

        <List />
    </section>
  </div>
</div>
</template>

<script>
import Header from './Header.vue'
import List from './List.vue'
import Nav from './Nav.vue'

export default {
  components: { List, Nav, Header },
  name: 'Structure',
  data: () => ({
    burgerValue: null,
  }),
  methods: {
    toggleBurger: function (value) {
      this.burgerValue = value;
      console.log(value);
    },
  }
}
</script>