<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="light" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Lorem ipsum dolor sit amet.</p>
    </Modal>
  </div>

  <div v-if="showModal2">
    <Modal2 theme="sale" @close="toggleModal2">
      <template v-slot:buttons>
          <button type="button">Submit</button>
      </template>
      <h1>Add your data...</h1>
      <form>
        <div class="form-group">
          <label for="name">Name</label>
          <input type="text" name="name" placeholder="your name...">
        </div>
        <div class="form-group">
          <label for="name">Email</label>
          <input type="text" name="email" placeholder="your email...">
        </div>
      </form>
    </Modal2>
  </div>
  <div class="group-button">
    <button @click.alt="toggleModal">Open Modal (alt)</button>
    <button @click="toggleModal2">Open Modal (another)</button>
  </div>
</template>

<script>
import Modal from './components/Modal.vue';
import Modal2 from './components/Modal2.vue';

export default {
  name: 'App',
  components: { Modal, Modal2 },
  data() {
    return {
      title: "My Firs vue apppp",
      header: 'sign up for the Giveaway!',
      text : 'Grab your ninja swag',
      showModal: false,
      showModal2 : false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2;
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

div.group-button{
  margin: 0 auto;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  width: 400px;
}

button {
  cursor: pointer;
  padding: 8px 16px;
  background: #03cfb4;
  border: 1px solid #03cfb4;
  color: white;
  border-radius: 8px;
  box-shadow: 15px 12px 23px -9px rgba(0,0,0,0.38);
  -webkit-box-shadow: 15px 12px 23px -9px rgba(0,0,0,0.38);
  -moz-box-shadow: 15px 12px 23px -9px rgba(0,0,0,0.38);
}

button:hover {
  filter: brightness(80%);
}
</style>
