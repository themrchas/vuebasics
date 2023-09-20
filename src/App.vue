<template>
  {{title}}
  <p>Click on backdrop to close modal...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">

      <!-- named slot example -->
      <template v-slot:links>
        <a href="#">link one</a>
        <a href="#">link two</a>
      </template>
      <h1>Here is a template being passed</h1>
      <p>Another tag being passed in same template</p>

    </Modal>
  </div>
  <button type="button" @click="toggleModal">open modal</button>
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
      header: "Prop passed to modal",
      text: "Text string passed to the modal",
      showModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
