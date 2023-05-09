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
    width: fit-content;
  }

  h1 {
    margin-left: $margin-left;
    margin-top: 1.25vh;
  }

  p {
    margin-left: $margin-left;
    margin-top: 0;
  }

  img {
    height: 6dvh;
  }

  .github-element {
    height: 6vh;
    justify-content: center;

    margin-top: 10px;
    margin-bottom: 10px;

    font-size: 125%;

    p {
      margin-top: 0;

      transform: translateY(50%);
    }
  }

  a {
    color: #E0E0E0;

    :hover {
      color: white;
    }

    text-decoration: none;
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
  <a href={github} target="_blank">
    <div class="github-element row">
      <img src={GithubLogo} alt="Didn't load">
      <p>GitHub</p>
    </div>
  </a>
</div>