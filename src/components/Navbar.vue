<template>
    <nav>
        <button class="btn" @click="openModal">Add Expence</button>
    </nav>
</template>

<script>
export default {
    name: 'Navbar',
    methods: {
        openModal(){
           this.$emit("modal-show"); 
        },
    },
};
</script>

<style scoped>
    nav{
        width: 100%;
        height: 60px;
        background: #fff;
        box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .btn{
        border: none; 
        border-radius: 3px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        background: #42b983;
        color: #fff;
        padding: 10px 15px;
        cursor: pointer;
        outline: none;
    }
</style>
