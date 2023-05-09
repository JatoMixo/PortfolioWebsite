<script>
  export let name = "";
  export let tool = "";
  export let description = "";
  export let github = "";

  import GithubLogo from "../images/tech/GithubLogo.png";
</script>

<style lang="scss">

  $margin-left: 0.75vw;
  $cyan-color: #00C5FF;

  .box {
    padding: 0;

    margin: 15px;
  }

  .animation {
    transform: translateY(0px);
    transition: transform 0.5s ease;

    width: fit-content;
  }

  .animation:hover {
    transform: translateY(-10px);
  }

  h1 {
    margin-left: $margin-left;
    margin-top: 1.25vh;

    font-size: 4vh;
  }

  p {
    margin-left: $margin-left;
    margin-top: 0;

    font-size: 85%;
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

  #inner-box {
    margin: -5px;

    margin-left: 100px;

    img {
      margin-top: 5px;
    }
  }
</style>

<div class="animation">
  <div class="box">
    <div class="row">
      <h1>{name}</h1>
      <div class="box" id="inner-box">
        <img src={tool} alt="Didn't load"/>
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
</div>