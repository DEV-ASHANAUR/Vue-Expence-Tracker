<template>
    <div>
        <div class="expences">
            <div class="balance">
                <span>Balance</span>
                <p>{{ allExpence.balance }}$</p>
            </div>
            <div class="income">
                <span>Income</span>
                <p>{{ allExpence.income }}$</p>
            </div>
            <div class="expence">
                <span>Expence</span>
                <p>{{ allExpence.expence }}$</p>
            </div>
        </div>
        <div class="history" v-for="(history,index) in allExpence.history" :key="index" :class="[history.number > 0 ? 'border-green':'border-red']">
           <div class="history__title">
               {{ history.title }}
            </div> 
            <div class="history__number">
               {{ history.number }}$
            </div> 
        </div>
    </div>
</template>

<script>
export default {
    name: 'Expences',
    props: ["allExpence"],
}
</script>

<style scoped>
    .expences{
        width: 800px;
        margin: 70px auto;
        display: flex;
        justify-content: space-between;
    }
    .balance{
        background: #ffffff;
        padding: 20px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        width: 200px;
        height: 150px;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        border-bottom: 4px solid orange;
    }
    .balance span {
        position: absolute;
        top: 0;
        left: 0;
        background: orange;
        color: #fff;
        font-size: 12px;
        padding: 5px;
    }
    .income{
        background: #ffffff;
        padding: 20px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        width: 200px;
        height: 150px;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        border-bottom: 4px solid #42b983;
    }
    .income span {
        position: absolute;
        top: 0;
        left: 0;
        background: #42b983;
        color: #fff;
        font-size: 12px;
        padding: 5px;
    }
    .expence{
        background: #ffffff;
        padding: 20px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        width: 200px;
        height: 150px;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        border-bottom: 4px solid #d4075d;
    }
    .expence span {
        position: absolute;
        top: 0;
        left: 0;
        background: #d4075d;
        color: #fff;
        font-size: 12px;
        padding: 5px;
    }
    .history{
        width: 800px;
        margin: 15px auto;
        background: #fff;
        padding: 12px;
        display: flex;
    }
    .history__title{
        width: 70%;
        text-transform: capitalize;
    }
    .history__number{
        width: 30%;
        text-align: right;
    }
    .border-green {
        border-left: 3px solid #42b983;
    }
    .border-red {
        border-left: 3px solid #d4075d;
    }
</style>