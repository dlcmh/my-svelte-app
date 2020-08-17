<script>
  import Navbar from './sections/navbar.svelte';

  let disabled = true;
  let name = '';
  let names = [];

  function keyPressed() {
    disabled = false;
  }

  function resetClicked() {
    disabled = true;
    names = [name, ...names];
    name = '';
  }
</script>

<Navbar title="vCard Generator" />

<form>
  <label>
    Name
    <input
      type="text"
      placeholder="Please enter your name"
      bind:value={name}
      on:keydown={keyPressed} />
  </label>

  <button {disabled} on:click|preventDefault={resetClicked}>Reset</button>
</form>

<p>{names}</p>
