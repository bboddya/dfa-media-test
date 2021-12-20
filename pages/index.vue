<template>
  <Structure/>
</template>

<script>
import Structure from '@/components/Structure.vue'
export default {
  components: { Structure },
  name: 'IndexPage'
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
  color: #fff;
  font-size: 12px;
  line-height: 15px;
}

a {
  text-decoration: none;
}

.container {
  padding: 0 56px 0 70px;

  &_body {
    background: #192233;
    padding: 0 23px 0 0;
    display: flex;
    min-height: 100vh;
    position: relative;
  }

  &_blue {
    background: #212C42;
    border-radius: 50px 50px 0px 0px;
    padding-top: 15px;
    padding-bottom: 30px;
    min-height: calc(100% - 121px);
  }
}

.btn {
  padding: 5px 10px;
  background: #212C42;
  color: #fff;
  cursor: pointer;
  border: none;
  transition: all .3s;
  border-radius: 3px;

  &:hover,
  &:focus {
    background: #ffffffa1;
    transition: all .3s;
  }

  &_modal {
    max-width: 100px;
    margin: 20px auto 0;
  }
}

.right {
  width: 100%;
  min-height: 100%;
}

.title {
  font-weight: bold;
  font-size: 40px;
  line-height: 47px;
}

@media screen and (max-width: 780px) {
  .container {
    &_body {
      padding: 0 20px;
    }

    &_blue {
      padding: 20px;
      border-radius: 15px 15px 0px 0px;
    }
  }
}

@media screen and (max-width: 576px) {
  .title {
    font-size: 24px;
    line-height: 32px;
  }

  .container {
    &_body {
      padding: 0 10px;
    }

    &_blue {
      padding: 20px 10px;
    }
  }
}
</style>