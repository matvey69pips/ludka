<template>
    <div class="left-container">
        <div class="dop-text">
            <h1 style=" font-family: XD; justify-self: center;">{{ props.name }}</h1>
            <p>{{ props.description }}</p>
            <p>{{ "Коеффицент: " + props.coefficient }}</p>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

interface Horse {
    name: string,
    description: string,
    coefficient: number,
    image: string,
}

const props = defineProps({

    name: {
        type: String,
        default: "Имя лошади"
    },
    description: {
        type: String,
        default: "описание лошади"
    },
   coefficient: {
        type: Number,
        default: 0
    }

})



</script>


<style>
.left-container {
    padding: 30px;
    height: 500px;
    background-color: rgb(37, 37, 120);
    border-radius: 10px;
    margin-top: 50px;

}

.dop-text {
    color: burlywood;
}
</style>