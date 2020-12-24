<template>
  <div v-if="status">
    <div class="modal" @click.self="toggle">
      <div class="modal__container">
          <div class="modal__form">
              <form @submit.prevent="addExpence">
                  <div class="modal__group">
                      <h3>Add Expence</h3>
                  </div>
                  <div class="modal__group">
                      <input type="text" class="modal__control" placeholder="Title..."
                      v-model="title" />
                  </div>
                  <div class="modal__group">
                      <input type="number" class="modal__control" placeholder="Expence..."
                      v-model="number" />
                  </div>
                  <div class="modal__group">
                      <input type="submit" value="Add Expence" class="button">
                  </div>
              </form>
          </div>
      </div>
    </div>
  </div>
  
</template>

<script>
export default {
    name: 'Modal',
    props: ['status'],
    data(){
        return {
            title: "",
            number: "",
        };
    },
    methods: {
        toggle (){
            this.$emit("model-toggle");
        },
        addExpence(){
            this.$emit("store-expence",{title: this.title, number: this.number});
            this.title = "";
            this.number = "";
        },
    },
}
</script>

<style scoped>
    .modal{
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1;
    }
    .modal__container {
        background: #fff;
        width: 450px;
        padding: 20px;
        border-radius: 5px;
    }
    .modal__group{
        margin: 15px 0;
    }
    .modal__control{
        border-bottom: 1px solid #42b983;
        border-left: none;
        border-right: none;
        border-top: none;
        width: 100%;
        padding: 7px 0;
        outline: none;
    }
    .button{
        border: none; 
        border-radius: 3px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        background: #42b983;
        color: #fff;
        padding: 10px 15px;
        cursor: pointer;
        width: 100%;
        outline: none;
    }
</style>