<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">Click Me</button> -->
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/>
  </div>
  <div v-if="showSecondModal">
    <Modal header="Sign Up For Our Newsletter" text="Get the latest news!" @close="toggleSecondModal" />
  </div>
  <button @click="toggleModal">Open Modal</button>
  <br>
  <button @click="toggleSecondModal">Open Second Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App', 
  components: {
    Modal
  },
  data() {
    return {
      title: "My First Vue App",
      header: "Sign Up for the Giveaway",
      text: "Half-price swag",
      showModal: false,
      showSecondModal: false
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleSecondModal() {
      this.showSecondModal = !this.showSecondModal
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
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
