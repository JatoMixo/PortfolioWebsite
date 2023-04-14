<script>
  export let name = "";
  export let image = "";
  export let description = "";
  export let link = "";
</script>

<style lang="scss">

  $default_box_width: 10%;

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

    transform: translateY(0px);
    transition: transform 0.5s ease;
  }

  .animation:hover {
    transform: translateY(-25px);
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

    text-shadow: 0 0 3px white;
  }
</style>

<!--{#if link == ""}
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
{/if}-->

<div class="animation">
  <a href={link}>
    <div class="box">
      <img src={image} alt="Didn't load"/>
      <h1>{name}</h1>
      <p>{description}</p>
    </div>
  </a>
</div>