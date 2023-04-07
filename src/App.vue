<script setup>
  import { ref } from "vue";
  import { v4 as uuidv4 } from 'uuid';
  import dayjs from 'dayjs';
  import relativeTime from 'dayjs/plugin/relativeTime';

  dayjs.extend(relativeTime)

  const getRandomLightColor = () => {
    let color = "hsl(" + Math.random() * 360 +", 100%, 75%)"
    return color
  }

  const showModal = ref(false)

  const toggleModal = () => showModal.value = !showModal.value

  const newNote = ref("")
  const notes = ref([])

  const addToNotes = () => {
    notes.value.push(
      {
        id: uuidv4(),
        text: newNote.value,
        date: new Date(),
        backgroundColor: getRandomLightColor()
      }
    )


    toggleModal()
    newNote.value = ""
  } 

</script>

<template>
  <main>
    <div id="overlay" v-if="showModal">
      <div class="modal">
        <textarea v-model="newNote" name="note" id="note" cols="30" rows="10"></textarea>
        <button id="add-note" @click="addToNotes">
          Add Note
        </button>
        <button id="close-add" @click="toggleModal">
          Close
        </button>
      </div>
    </div>
    
    <div class="container">
      <header>
        <h1 id="app-text">Yo Notes</h1>
        <button id="add-btn" @click="toggleModal" >+</button>
      </header>
      <div class="cards-container">
        <div v-for="note in notes" :key="note.id" class="card" :style="{backgroundColor: note.backgroundColor}" >
          <p class="card-text">
            {{ note.text }}
          </p>
          <p class="muted-text">{{ dayjs(note.date.toString()).toNow() }}</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
  main {
    height: 100vh;
    width: 100vw;
  }

  .container {
    max-width: 1000px;
    padding: 0.5rem;
    margin: 0 auto;
  }

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  #app-text {
    font-weight: bold;
    margin-bottom: 0.5rem;
    font-size: 4rem;
  }

  #add-btn {
    border: none;
    border-radius: 100%;
    width: 2rem;
    height: 2rem;
    cursor: pointer;
    color: white;
    background-color: rgb(52, 103, 214);
    font-size: 1rem;
  }

  .card{
    width: 16rem;
    height: 16rem;
    padding: 1rem;
    border-radius: 1rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-right: 0.5rem;
    margin-bottom: 0.5rem;
    color: black;
  }

  .muted-text{
    font-size: small;
    font-weight: bold;
    color: grey;
  }

  .cards-container{
    display: flex;
    flex-wrap: wrap;
  }

  #overlay{
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.77);
    z-index: 3;
    display: flex;
    align-items: center;
    align-content: center;
  }

  .modal {
    width: 50rem;
    background-color: white;
    border-radius: 1rem;
    padding: 1rem;
    position: relative;
    display: flex;
    flex-direction: column;
    margin: auto;
  }

  #add-note{
    padding: 1rem 2rem;
    font-size: 2rem;
    cursor: pointer;
    width: 100%;
    color: white;
    background-color: blueviolet;
    margin-top: 1rem;
    border: none;
  }

  #close-add{
    padding: 1rem 2rem;
    font-size: 2rem;
    cursor: pointer;
    width: 100%;
    color: white;
    background-color: rgb(222, 81, 81);
    margin-top: 1rem;
    border: none;
  }
</style>