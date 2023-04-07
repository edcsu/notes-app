<template>
  <main>
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
</style>