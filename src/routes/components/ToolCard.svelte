<script>
  export let name = "";
  export let image = "";
  export let description = "";
</script>

<style lang="scss">

  $image-height: 0px; // To change later
  $default_box_width: 10%;

  .box {
    width: 175px;
    height: 390px; // 390 looks nice
    padding-bottom: 0;

    img {
      // height: 15dvh;
      height: 150px;

      display: block;
      margin-left: auto;
      margin-right: auto;
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

  p {
    font-size: 16px;
  }

  h1 {
    text-align: center;
    font-size: 28px;

    text-shadow: 0 0 3px white;
  }
</style>

<div class="animation">
  <div class="box">
    <img src={image} alt="Didn't load"/>
    <h1>{name}</h1>
    <p>{description}</p>
  </div>
</div>