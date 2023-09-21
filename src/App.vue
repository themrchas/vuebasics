<template>
  {{title}}
  <p>Click on backdrop to close modal...</p>

  <!-- telepost uses css selector to determine where to mount item -->
  <teleport to="div.modals" v-if="showModalOne">
    <Modal theme="" @close="toggleModalOne">

      <!-- named slot example -->
      <template v-slot:links>
        <a href="#">link one</a>
        <a href="#">link two</a>
      </template>

      <h1>Here is a template being passed to Modal One</h1>
      <p>Another tag being passed in same template</p>

    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo">

      <!-- named slot example -->
      <template v-slot:links>
        <a href="#">link one</a>
        <a href="#">link two</a>
      </template>

      <h1>Here is a template being passed to Modal Two</h1>
      <p>Another tag being passed in same template</p>

    </Modal>
  </div>

  <div id="btnContainer">
    <button type="button" @click="toggleModalOne">Open modal one</button>
    <button type="button" @click="toggleModalTwo">Open modal two</button>
  </div>




</template>

<script>

import Modal from './components/Modal'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: "Here is a Vue app",
      showModalOne: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModalOne() {
      this.showModalOne = !this.showModalOne;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    }
  }
}
</script>

<style>
#app ,.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#btnContainer {
  display: flex;
  justify-content: space-around;
  width: 400px;
  margin: 100px auto;
}
</style>
