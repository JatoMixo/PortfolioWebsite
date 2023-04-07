<script>
  export let name = "";
  export let image = "";
  export let description = "";
  export let link = "";
</script>

<style lang="scss">

  $default_box_width: 10%;

  @keyframes on_hover {
    0% {top: 0px}
    100% {top: -25px}
  }

  .box {
    width: fit-content;
    height: fit-content;

    img {
      height: 100%;
      width: 100%;
    }
  }

  .animation {
    width: $default_box_width;
  }

  .animation:hover {
    position: relative;

    animation-name: on_hover;
    animation-duration: 0.5s;
    animation-fill-mode: forwards;
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

<!--{#if link != ""}
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
{/if}-->

{#if link == ""}
<div class="animation">
  <div class="box">
    <img src={image} alt="Didn't load"/>
    <h1>{name}</h1>
    <p>{description}</p>
  </div>
</div>
{:else}
<div class="animation">
  <a href={link}>
    <div class="box">
      <img src={image} alt="Didn't load"/>
      <h1>{name}</h1>
      <p>{description}</p>
    </div>
  </a>
</div>
{/if}