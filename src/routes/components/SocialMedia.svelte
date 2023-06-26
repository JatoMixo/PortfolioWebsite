<script>
  export let link = "";
  export let image = "";
  export let image_alt = "";
</script>

<style lang="scss">
  a {
    width: 100%;
    min-width: 50px;
    height: auto;
  }

  img {
    width: 4dvw;
    min-width: 50px;

    margin: 0px;

    opacity: 0.6;

    $transition-duration: 0.15s;
    transition: opacity $transition-duration, width $transition-duration, height $transition-duration;
  }

  img:hover {
    width: 5dvw;

    opacity: 1;
  }
</style>

<a href={link} target="_blank">
  <img src={image} alt={image_alt}/>
</a>