<script>
  const leftArrow = "";
  let command = "";

  let commandInputField;

  let commandsExecuted = [];

  const correctCommandStatus = "#00FFCA";
  const wrongCommandStatus = "#FF0000";

  function Command(commandExecuted) {
    this.command = commandExecuted;

    this.getResult = () => {
      if (this.command == "help") {
        return [
          "- Why did you learn to code?",
          "- How did you learn to code?",
          "- Did you learn everything by yourself?",
        ];
      }

      return "";
    }
  }

  async function addCommand(event) {
    let key = event.key;
    const RETURN_KEY = "Enter";

    if (key != RETURN_KEY) {
      return;
    }

    commandsExecuted.push(new Command(command));
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

      transform: TranslateY(20%);

      font-size: 2.65vh;
    }

    .command-result {
      font-size: 2.5vh;

      margin-left: 1.5vw;
    }

    input {
      width: 100%;

      font-size: 75%;

      color: whitesmoke;
      font-family: "Hack Nerd Font";

      border-width: 0px;

      background-color: $secondary_background_color;

      text-shadow: 0 0 3px;
      text-decoration: none;

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

<svelte:window on:keydown={addCommand}></svelte:window>

<div class="terminal box">
  <p>Hello! I'm <span class="blue-flash">JatoMixo</span>, a High School Student who loves <span class="yellow-flash">programming</span> stuff</p>
  <p>Type <span class="green-flash">help</span> to know more about me</p>
  {#each commandsExecuted as command}
    <div class="row">
      <p style="font-size: 150%; color: {(command.getResult() != "") ? correctCommandStatus : wrongCommandStatus};">{leftArrow}</p>
      <p class="command">{command.command}</p>
    </div>
    {#each command.getResult() as sentence}
      <p class="command-result">{sentence}</p>  
    {/each}
  {/each}
  <div class="row">
    <p style="font-size: 150%;">{leftArrow}</p>
    <input spellcheck="false" bind:value={command} bind:this={commandInputField}>
  </div>
</div>