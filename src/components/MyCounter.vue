<template>
    <div>
            <h1 class="title">Vuex Counter</h1>
            <h1 class="counter">{{counter}}</h1>
            <button @click="SubtratToCounter(parseInt(value))">-</button>
            <input type="number" v-model="value"/>
            <button @click="addToCounter(parseInt(value))">+</button>
            <div>
                <button class="btn" @click="addRandomNumber">Add a Random Number</button>
            </div>
    </div>
</template>
<script>
import {mapState, mapMutations, mapActions} from "vuex";


export default {
    data(){
        return{
                value: 0,
        }
    },
    computed:{
            ...mapState(["counter"])
        },
    methods:{
        ...mapMutations(["addToCounter", "SubtratToCounter"]),
        ...mapActions(["addRandomNumber"])
    },

}
</script>
<style>
  .title{
  margin-top: -23px;
}
  .counter{
    font-size: 3rem;
  }
  button{
    border-radius: 100%;
    border: none;
    width: 2rem;
    height: 2rem;
    font-weight: 700px;
    cursor: pointer;
  }
  input{
    text-align: center;
    margin: 0 0.5rem;
    padding: 0.4rem;
  }
  .btn{
    border-radius: 0.5rem;
    width: auto;
    background-color: #41B983;
    margin-top: 1rem;
    color: white;
    cursor: pointer;
  }
</style>
  