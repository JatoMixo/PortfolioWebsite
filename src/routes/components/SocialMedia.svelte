<script>
  export let link = "";
  export let image = "";
  export let image_alt = "";
</script>

<style lang="scss">
  a {
    width: 3dvw;
    min-width: 50px;
    height: auto;
  }

  img {
    width: 100%;
    height: 100%;

    margin: 0px;

    opacity: 0.6;

    $transition-duration: 0.15s;
    transition: opacity $transition-duration, width $transition-duration, height $transition-duration;
  }

  img:hover {
    width: 110%;
    height: 110%;

    opacity: 1;
  }
</style>

<a href={link} target="_blank">
  <img src={image} alt={image_alt}/>
</a>