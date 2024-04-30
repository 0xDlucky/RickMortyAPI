<script setup>
const personagem = defineProps(["name", "url", "gender", "species", "location", "episode"])
const personagemId = personagem.url.split('/')[5]
const imageUrl = "https://rickandmortyapi.com/api/character/avatar/" + personagemId + ".jpeg"
console.log(imageUrl)

</script>

<template>
  <div class="col-md-4">
    <div class="card p-2 mb-3" id="card">
      <img :src="imageUrl" height="280" alt="">
      <p class="text-center"><strong>Nome:</strong> {{ personagem.name }}</p>
      <p class="text-center"><strong>Gênero:</strong> {{ personagem.gender }}</p>
      <p class="text-center"><strong>Espécie:</strong> {{ personagem.species }}</p>
      <p class="text-center"><strong>Último Local:</strong> {{ personagem.location.name }}</p>
      <p class="text-center"><strong>Último episódio:</strong> {{ personagem.episode.length }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageUrl: 'https://example.com/path/to/image.jpg',
      personagem: {
        name: 'John Doe',
        gender: 'Male',
        species: 'Human',
        location: {
          name: 'Earth'
        },
        episode: ['Episode 1', 'Episode 2', 'Episode 3']
      }
    };
  }
};
</script>

<style>
.text-center {
  font-family: Arial, sans-serif;
  color: #42b983;
  text-align: center;
}
</style>
