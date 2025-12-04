<template>
    <div class="right-container">
        <div class="text-up">
            <p> Сумма ставочки</p>
        </div>
        <div>
            <div class="text-field">
                <v-text-field type="number" v-model="betValue" hide-details variant="plain"></v-text-field>
            </div>
            {{ props.coefficient }}
            <div class="coefficient-text">
                <p>сумма выйграша:</p>
                <p style="font-size: 15px; color: greenyellow;">{{Math.floor( props.coefficient * betValue )}}</p>
            </div>
            <div class="BIG-BUTTON">

            </div>
        </div>

    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const number = 200
const props= defineProps({
    coefficient:{
        type: Number,
        default: 0
    }
})

const betValue = ref(0) 


</script>

<style>
.BIG-BUTTON{
    width: 100%;
}

.text-field {
    background-color: rgb(52, 52, 153);
    padding: 0%;
    padding-left: 10px;
    padding-right: 10px;
    padding-bottom: 14px;
    border-radius: 20px;
}

.text-up {
    text-align: end;
    font-family: XD;
    font-size: 15px;
    color: burlywood;

}

.right-container {
    padding: 30px;
    height: 500px;
    background-color: rgb(37, 37, 120);
    border-radius: 10px;
    margin-top: 50px;

}
.coefficient-text{
    text-align: end;
 font-family: XD;
  color: burlywood;
  font-size: 10px;
}
.text-field input[type="number"]::-webkit-outer-spin-button,
.text-field input[type="number"]::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
