<script>
  export let name = "";
  export let tool = "";
  export let description = "";
  export let github = "";

  import GithubLogo from "../images/GithubLogo.png";
</script>

<style lang="scss">

  $margin-left: 0.75vw;
  $cyan-color: #00C5FF;

  h1 {
    font-size: 4vh;

    margin-left: 0.1vw;
    margin-top: 0.1vw;
  }

  .box {
    padding: 0;

    width: 20%;
  }

  .inner-box {
    margin-right: 0;
    margin-top: 0;

    transform: translate(0.25vw, -0.5vh);

    position: relative;
    float: right;
  }

  h1 {
    margin-left: $margin-left;
    margin-top: 1.25vh;
  }

  p {
    margin-left: $margin-left;
    margin-top: 0;
  }
</style>

<div class="box">
  <div class="row">
    <h1>{name}</h1>
    <div class="box inner-box">
      <img src={tool} alt="Didn't load" style="width: 3vw;"/>
    </div>
  </div>
  <p>{description}</p>
  <hr>
  <div class="row">
    <img src={GithubLogo} alt="Didn't load">
    <p>GitHub</p>
  </div>
</div>