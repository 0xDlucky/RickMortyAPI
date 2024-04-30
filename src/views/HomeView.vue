<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListPersonagens from '../components/ListPersonagens.vue';

let personagens = reactive(ref());

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results
    console.log(personagens)
  })
})

</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-12">
          <div class="card">
            <div class="card-body row">
            <ListPersonagens 
            v-for="personagem in personagens" 
            :key="personagem.name" 
            :name="personagem.name"
            :url="personagem.url"
            :gender="personagem.gender"
            :species="personagem.species"
            :location="personagem.location"
            :episode="personagem.episode"
            />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
  <footer class="text-light">
    <div>
      Unimar | ADS | {{ new Date().getFullYear() }}
    </div>
  </footer>
</template>

<style>
body{
  background: #081119;
background-image: url("~@/assets/background.gif");
}
.card-body{
  background: #002128;
}
footer{
    bottom: 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
    color: #000;
  }
  h1 {
color: #00ff97;
}
  @media screen and (max-width: 918px) {
.content {
grid-template-columns: 1fr 1fr;
}
.character {
display: flex;
align-items: center;
}
h2{
font-size: 1rem;
}
}
@media screen and (max-width: 540px) {
.content {
width: 90%;
grid-template-columns: 1fr;
}
.character {
display: flex;
align-items: center;
}

}
</style>
