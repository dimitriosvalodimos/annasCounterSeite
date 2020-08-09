<script>
  let counter = 0;
  let inputField = "";

  const convertNumber = (e) => {
    let result = 0;
    if (e.key === "Enter") {
      counter = Number(inputField);
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
  button {
    width: 50%;
    border: none;
    filter: drop-shadow(0px 5px 5px rgba(0, 0, 0, 0.25));
    padding: 1rem;
    margin: 3rem;
  }
</style>

<div class="app">
  <h1 class="title">Annas komische Seite</h1>
  <div class="content">
    <h2 class="counterShow">Counter: {counter}</h2>
    <button
      on:click={(e) => {
        counter++;
      }}>
      +1
    </button>
    <label for="counterSet">Set counter to:</label>
    <input
      type="text"
      id="counterSet"
      bind:value={inputField}
      on:keypress={convertNumber} />
  </div>
</div>
