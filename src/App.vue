<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <h1>Information!</h1>
      <p>I'm now learning VueJS</p>
      <template v-slot:links>
          <a href="https://www.rifgialhakim.biz.id">More Info</a>
      </template>
    </Modal>
  </teleport>
  <teleport to="#modals" v-if="showModalTwo">
    <Modal theme="" @close="toggleModalTwo">
      <h1>Informasi!</h1>
      <p>Saya sedang belajar VueJS</p>
      <template v-slot:links>
        <a href="https://www.rifgialhakim.biz.id">Info Lainnya</a>
      </template>
    </Modal>
  </teleport>
  <button @click="toggleModal">Open Modal (Eng)</button>&nbsp;
  <button @click="toggleModalTwo">Buka Modal (Id)</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: "My First Vue App",
      header: "Sign up for the giveaway!",
      text: "Grab your ninja swag for half price!",
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
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
