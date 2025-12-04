<script setup lang="ts">
import { ref } from 'vue'
import LeftContainerCard from './components/common/LeftContainerCard.vue'
import RightContainerCard from './components/common/RightContainerCard.vue'
// const number = 123
// const string = "qweddd"
// const object = {
// }

interface Horse{
    name: String,
    description: String,
    coefficient: Number,
    image: String,
}

const selectedHorse = ref<Horse>()

const horses = [
  {
    name: "Астра",
    description: "Самая быстрая лошадь на диком западе",
    coefficient: 1.2,
    image: "/src/assets/images/photo_4_2025-11-24_19-19-37.jpg",
  },
  {
    name: "Юлий",
    description: "С детства рос с циганями ",
    coefficient: 2.3,
    image: "/src/assets/images/photo_3_2025-11-24_19-19-37.jpg"
  },
  {
    name: "Кочерга",
    description: "Не любимая богом",
    coefficient: 10.1,
    image: "/src/assets/images/photo_5_2025-11-24_19-19-37.jpg"
  },
  {
    name: "Бойбик",
    description: "Спутали с собакой",
    coefficient: 2.3,
    image: "/src/assets/images/photo_2_2025-11-24_19-19-37.jpg"
  },
  {
    name: "Толик",
    description: "ТОЛИК еболик первый день на работе бляяя",
    coefficient: 5.2,
    image: "/src/assets/images/photo_1_2025-11-24_19-19-37.jpg"
  },
  {
    name: "Сынш Люхи",
    description: "Без коментариев",
    coefficient: 1.5,
    image: "/src/assets/images/photo_6_2025-11-24_19-19-37.jpg"
  }
]

// const

</script>

<template>


  <div class="main-container">

    <div class="side-col">
      <LeftContainerCard :name="selectedHorse?.name" :description="selectedHorse?.description" :coefficient="selectedHorse?.coefficient"/>
    </div>



    <div class="central-col">
      <h1 class="title">Lydka </h1>
      <p class="text">Баланс:10000$</p>

      <div class="card-container">
        <!-- <img src="./assets/images/photo_4_2025-11-24_19-19-37.jpg">  -->
        <div class="card" v-for="horse in horses" @click="selectedHorse = horse">
          <div>
            <img class="image-card" :src="horse.image">
          </div>
          <p class="name-card">{{ horse.name }}</p>
        </div>

      </div>

    </div>




    <div class="side-col">
    <RightContainerCard  :coefficient="selectedHorse?.coefficient"/>
    </div>

  </div>



</template>






<style scoped>
@font-face {
  font-family: XD;
  src: url(./assets/fonts/Y224.otf);
}

.image-card {
  height: 80px;
  width: 80px;
}



.side-col {
  min-width: 300px;
  max-width: 300px;
}
.title {
  text-align: center;
  font-size: 60px;
  font-weight: 200;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  background-image: linear-gradient(to top, rgb(169, 43, 43), rgb(247, 14, 14));
  ;
  margin: 0%;
  color: rgb(246, 246, 246);
}

.main-container {
  justify-items: center;
  margin: 0%;
  padding: 0%;
  background-color: rgb(8, 8, 23);
  display: flex;
  justify-content: space-around;
}

.text {
  color: rgb(251, 245, 238);
  font-size: 30px;
  margin-top: 50px;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
}

.card {
  width: 110px;
  height: 130px;
  background-color: rgb(37, 37, 120);
  margin: 30px;
  border-radius: 10px;
  align-content: end;
  justify-items: center;

  transition: cubic-bezier(.56, .81, .44, 1.31) 0.3s;
}

.card:hover {
  scale: 1.557;
box-shadow: 0px 0px 40px 13px rgba(255, 255, 255, 0.4);
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin-top: 60px;
  height: 50vh;
  width: 530px;

}

.name-card {
  margin: 5px;
  width: fit-content;
  font-family: XD;
  font-size: 9px;
  color: burlywood;
}
</style>
