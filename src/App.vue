<template>
  <h1>My first Vue app</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal"> <!-- close is the name of emitted event from Modal component !-->
      <!-- Using Slots to pass content (template in this case) to component -->
        <h1>Mythose GiveAway</h1>
        <p>Grap your Mytose swag for half price!</p>
    </Modal>
  </div>
  <button @click.shift="toggleModal">Open Modal (shift)</button><br><br>
  <button @click.right="toggleModal">Open Modal (right click)</button><br><br>
  <button @click.alt="toggleModal">Open Modal (alt)</button>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  name: "App",
  components: {
    Modal
  },
  data() {
    return {
      title: '',
      header: 'Signup for the GiveAway!',
      text: 'Grab your modal for half price!',
      showModal: false
    }
  },
  methods: {
    toggleModal () {
      this.showModal = !this.showModal;
    }
  }
};
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
h1 {
  color: yellow;
}
</style>
