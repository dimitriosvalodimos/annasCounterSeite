<script>
  // localStorage is a way to have "persistent" storage of simple infos
  // even after closing the webapp.
  let count = localStorage.getItem("annasCounter") || 0;

  let inputField = "";

  const increment = (e) => {
    count++;
    localStorage.setItem("annasCounter", count);
  };

  const decrement = (e) => {
    count--;
    localStorage.setItem("annasCounter", count);
  };

  const setNumber = (e) => {
    if (e.key === "Enter") {
      count = isNaN(Number(inputField)) ? 0 : Number(inputField);
      localStorage.setItem("annasCounter", count);
    }
  };
</script>

<style>
  .app {
    display: grid;
    width: 100%;
    justify-content: space-around;
    text-align: center;
  }

  .counterShow {
    font-size: 4rem;
  }
  button {
    width: 50%;
    border: none;
    filter: drop-shadow(0px 5px 5px rgba(0, 0, 0, 0.25));
    padding: 1rem;
    margin: 2rem;
  }
</style>

<div class="app">
  <div class="content">
    <h2 class="counterShow">{count}</h2>
    <button on:click={increment}>+1</button>
    <button on:click={decrement}>-1</button>
    <label for="counterSet">Set counter to:</label>
    <input
      type="text"
      id="counterSet"
      bind:value={inputField}
      on:keypress={setNumber} />
  </div>
</div>
