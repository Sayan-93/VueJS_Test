<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign here</a>
      </template>
      <h1>Sign up</h1>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo">
      <h1>Sign up for the newsletter</h1>
    </Modal>
  </div>

  <button @click="toggleModal">open modal</button>
  <button @click="toggleModalTwo">open modal</button>
  
  
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return{
      title: 'New Vue project',
      header: 'Sign up!',
      text: 'Good luck',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
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
h1 {
  border-bottom: 10px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
