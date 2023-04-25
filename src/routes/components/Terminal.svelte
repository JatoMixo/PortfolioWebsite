<script>
  const leftArrow = "";
  let command = "";

  let commandInputField;

  let commandsExecuted = [];

  const correctCommandStatus = "#00FFCA";
  const wrongCommandStatus = "#FF0000";

  let lineStatus = correctCommandStatus;

  async function processCommand(event) {
    let key = event.key;

    const RETURN_KEY = "Enter";

    if (key != RETURN_KEY) {
      return;
    }

    commandsExecuted.push(command);
    commandsExecuted = commandsExecuted;

    commandInputField.value = "";
  }
</script>

<style lang="scss">
  .box {
    padding: 10px;
    background-color: $secondary_background_color;

    p {
      margin: 0;
    }

    .command {
      display: block;

      transform: TranslateY(15%);

      font-size: 3vh;
    }

    input {
      width: 100%;

      font-size: 75%;

      color: whitesmoke;
      font-family: "Hack Nerd Font";

      border-width: 0px;

      background-color: $secondary_background_color;

      text-shadow: 0 0 3px;

      outline: none;
    }
  }

  .green-flash {
    $green-color: #00FFCA;
    color: $green-color; 

    text-shadow: 0 0 10px $green-color;
  }

  .blue-flash {
    $blue-color: #1f2799;
    color: $blue-color;

    text-shadow: 0 0 10px $blue-color;
  }

  .yellow-flash {
    $yellow-color: #FFC857;
    color: $yellow-color;

    text-shadow: 0 0 10px $yellow-color;
  }
</style>

<svelte:window on:keydown={processCommand}></svelte:window>

<div class="terminal box">
  <p>Hello! I'm <span class="blue-flash">JatoMixo</span>, a High School Student who loves <span class="yellow-flash">programming</span> stuff</p>
  <p>Type <span class="green-flash">help</span> to know more about me</p>
  {#each commandsExecuted as command}
    <div class="row">
      <p style="font-size: 150%; color: {lineStatus};">{leftArrow}</p>
      <p class="command">{command}</p>
    </div>
  {/each}
  <div class="row">
    <p style="font-size: 150%; color: {lineStatus};">{leftArrow}</p>
    <input type="text" bind:value={command} bind:this={commandInputField}>
  </div>
</div>