<template>
  <h1>My first Vue app</h1>
  <p>Welcome ...</p>

  <teleport to=".modals" v-if="showModal">
    <Modal @close="toggleModal">
      <template v-slot:links> 
        <a href="#">Signup now</a>
        <a href="#">More info</a>
      </template>

      <h1>Mythose GiveAway</h1>
      <p>Grap your Mytose swag for half price!</p>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
        <h1>Sign up for the newsletter</h1>
        <p>For updates and promo codes!</p>
    </Modal>
  </div>


  <button @click="toggleModal">Open Modal</button> <br> <br>
  <button @click="toggleModalTwo">Open Modal Two</button>
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
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal () {
      this.showModal = !this.showModal;
    },
    toggleModalTwo () {
      this.showModalTwo = !this.showModalTwo;
    }
  }
};
</script>

<style>
#app, .modals {
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
