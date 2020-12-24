<template>
  <Navbar @modal-show="modalToggle" />
  <Modal @model-toggle="modalToggle" :status="modalStatus" @store-expence="storeExpence" />
  <Expences :allExpence="expences" />
</template>

<script>
import Navbar from './components/Navbar'
import Modal from './components/Modal'
import Expences from './components/Expences'
export default {
  name: 'App',
  components: {
    Navbar,
    Modal,
    Expences
  },
  data(){
    return{
      modalStatus:false,
      expences: {
        balance: 0,
        income: 0,
        expence: 0,
        history: [],
      },
    };
  },
  methods: {
    modalToggle(){
       this.modalStatus = !this.modalStatus;
    },
    storeExpence(payload){
      const number = parseInt(payload.number);
      // console.log(typeof number);
      if(number > 1){
        this.expences = {
          ...this.expences,
          income: this.expences.income + number,
          balance: this.expences.balance + number,
          history: [{ title: payload.title, number}, ...this.expences.history]
        }
      } else if(number < 1){
        this.expences = {
          ...this.expences,
          expence: this.expences.expence + number,
          balance: this.expences.balance + number,
          history: [{ title: payload.title, number}, ...this.expences.history]
        }

      }
      this.modalStatus = false;
    },
  },
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
