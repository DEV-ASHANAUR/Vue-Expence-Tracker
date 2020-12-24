<template>
  <Navbar @modal-show="modalToggle" />
  <Modal @model-toggle="modalToggle" :status="modalStatus" />
</template>

<script>
import Navbar from './components/Navbar'
import Modal from './components/Modal'
export default {
  name: 'App',
  components: {
    Navbar,
    Modal
  },
  data(){
    return{
      modalStatus:false,
    };
  },
  methods: {
    modalToggle(){
       this.modalStatus = !this.modalStatus;
    }
  }
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  background: #fafafa;
}
</style>
