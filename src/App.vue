<template>
  <h1>{{ title }}</h1>
  <!-- <input type="text" ref="name" /> -->
  <div v-if="showModal">
    <ModalComponent :theme="theme" @close="handleModalDisplay">
      <h1>Sign up for the Giveaway!</h1>
      <p>Grab my vue course material 50% off price</p>
      <template v-slot:social>
        <a href="#">Linkedln</a>
        <a href="#">Twitter</a>
      </template>
    </ModalComponent>
  </div>
  <button @click.alt="handleModalDisplay">Show Modal (left click + alt)</button>
  <!-- <SlotComponent>
    <h1>This is a slot component</h1>
    <template v-slot:links>
      <a href="#">Linkedln</a>
      <a href="#">Twitter</a>
    </template>
  </SlotComponent> -->
</template>

<script>
import ModalComponent from "./components/ModalComponent.vue";
// import SlotComponent from "./components/SlotComponent.vue";
export default {
  name: "App",
  components: {
    ModalComponent,
    // SlotComponent,
  },
  data() {
    return {
      title: "My First Vue App :)",
      theme: "sale",
      showModal: false,
      message: "How are you doing modal",
    };
  },
  methods: {
    // handleClick() {
    //   console.log(this.$refs.name);
    //   this.$refs.name.classList.add("active");
    //   this.$refs.name.focus();
    // },
    handleModalDisplay() {
      this.showModal = !this.showModal;
    },
  },
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
</style>
