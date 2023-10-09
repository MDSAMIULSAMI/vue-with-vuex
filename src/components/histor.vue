<template>
    <div>
        <h2 class="container">History of Change</h2>
        <div class="flex">
                <p v-for="(number,index) in history " :key="index" :class="activeIndexes(parseInt(value)).includes(index) && 'bold'">
                    {{number}}
                </p>
        </div>
        <!-- <p> indexes: {{ activeIndexes(value) }}</p> -->
        <input type="number" placeholder="Search by Value....." v-model="value">
    </div>
</template>
<script>
import {mapState, mapGetters} from "vuex";
export default {
    data(){
        return{
            value: ''
        }
    },
    computed:{
        ...mapState(["history"]),
        ...mapGetters(["activeIndexes"])
    }
}
</script>
  
<style>
.container{
    margin-top: 7rem;
    display: flex;
    justify-content: center;
    align-items: center;
}
.flex{
    display: flex;
    width: 25rem;
    text-align: center;
    margin: 0 auto;
    justify-content: center;
    flex-wrap: wrap;
}
.flex p{
    margin: 1rem;
}
.bold{
    font-weight: 900;
    background-color: chartreuse;
}
</style>
  