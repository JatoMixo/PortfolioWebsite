<script>
  export let name = "";
  export let image = "";
  export let description = "";
  export let link = "";
</script>

<style lang="scss">

  @keyframes on_hover {
    0% {top: 0px}
    100% {top: -25px}
  }

  div {
    /* BORDER */
    border: solid 5px #ff5555;
    border-radius: 10px;
    box-shadow: 0 0 10px #ff5555;

    /* SIZE */
    width: 10%;
    height: fit-content; // 260px

    /* PADDING */
    padding: 15px;

    /* COLOR */
    background-color: #1D1D1D;

    /* IMAGE INSIDE */
    img {
      position: relative;

      display: block;
      margin-left: auto;
      margin-right: auto;

      height: 100%;
      width: 100%;
    }

    :hover {
      animation-name: on_hover;
      animation-duration: 0.5s;
    }
  }

  a {
    color: white;
    text-decoration: none;
  }

  p {
    font-size: 16px;
  }

  h1 {
    text-align: center;
    font-size: 28px;
  }
</style>

{#if link != ""}
<div>
  <a href={link}>
    <img src={image} alt="Didn't load"/>
    <h1>{name}</h1>
    <p>{description}</p>
  </a>
</div>
{:else}
  <div>
    <img src={image} alt="Didn't load"/>
    <h1>{name}</h1>
    <p>{description}</p>
  </div>
{/if}