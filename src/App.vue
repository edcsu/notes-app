<template>
  <main>
    <!-- <div id="overlay">
      <div class="modal">
        <textarea name="note" id="note" cols="30" rows="10"></textarea>
        <button id="add-note">
          Add Note
        </button>
        <button id="close-add">
          Close
        </button>
      </div>
    </div> -->
    <div class="container">
      <header>
        <h1 id="app-text">Yo Notes</h1>
        <button id="add-btn">+</button>
      </header>
      <div class="cards-container">
        <div class="card">
          <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi nobis dignissimos iste pariatur eum consequuntur voluptatem quisquam esse modi, alias illo corporis reiciendis. Aliquid harum excepturi voluptate vel, consectetur soluta.</p>
          <p class="muted-text">04/28/2033</p>
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
    background-color: rgb(21, 20, 20);
    font-size: 1rem;
  }

  .card{
    width: 16rem;
    height: 16rem;
    background-color: yellowgreen;
    padding: 1rem;
    border-radius: 1rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-right: 0.5rem;
    margin-bottom: 0.5rem;
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