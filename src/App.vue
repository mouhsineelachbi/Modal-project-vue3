<template>
  <h1>My first Vue app</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal"> <!-- close is the name of emitted event from Modal component !-->
      <!-- Using Slots to pass content (template in this case) to component -->

      <!-- named slot -->
      <template v-slot:links> <!-- links is the name of the slot -->
        <a href="#">Signup now</a>
        <a href="#">More info</a>
      </template>

      <!-- unnamed slot -->
        <h1>Mythose GiveAway</h1>
        <p>Grap your Mytose swag for half price!</p>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo"> <!-- close is the name of emitted event from Modal component !-->
      <!-- Using Slots to pass content (template in this case) to component -->
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
