<template>
  <h1>My first Vue app</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> <!-- close is the name of emitted event from Modal component !-->
  </div>
  <button @click="toggleModal">Open Modal</button>
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
