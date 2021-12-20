<template>
  <header class="header">
    <div @click="toggleBurger" class="burger"
      :class="{
        'active': burger
      }"
    >
      <div class="burger__line"></div>

      <div class="burger__line"></div>

      <div class="burger__line"></div>
    </div>

    <div class="breadcrumbs">Мероприятия</div>

    <button class="btn header__btn" @click="modal = !modal">Связаться с нами</button>

    <Modal v-if="modal" @toggleModal="toggleModal" />
  </header>
</template>

<script>
import Modal from './Modal/Modal.vue'

export default {
  components: { Modal },
  name: 'Header',
  data: () => ({
    modal: false,
    burger: false,
  }),
  methods: {
    toggleModal: function (value) {
      this.modal = value;
    },
    toggleBurger: function () {
      this.burger = !this.burger;
      this.$emit('toggleBurger', this.burger)
    },
  }
}
</script>

<style lang="scss">
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 35px 56px 61px 72px;
}

.burger {
  display: none;
  width: 20px;

  &__line {
    width: 100%;
    height: 1px;
    background: #fff;
    transition: all .3s;

    &:not(:last-child) {
      margin-bottom: 5px;
    }
  }

  &.active {
    .burger__line:first-child {
      transform: rotate(45deg);
      margin-bottom: -1px;
      transition: all .3s;
    }

    .burger__line:nth-child(2) {
      display: none;
    }

    .burger__line:last-child {
      transform: rotate(-45deg);
      margin-bottom: 0;
      transition: all .3s;
    }
  }
}

@media screen and (max-width: 992px) {
  .header {
    padding: 20px 0;
  }
}

@media screen and (max-width: 780px) {
  .burger {
    display: block;
    order: 1;
  }

  .header__btn {
    order: -1;
  }
}
</style>