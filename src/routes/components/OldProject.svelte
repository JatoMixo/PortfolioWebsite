<script>
  export let name = "";
  export let tool = "";
  export let description = "";
  export let github = "";

  import GithubLogo from "/src/routes/images/tech/GithubLogo.png";
</script>

<style lang="scss">

  $margin-left: 10px;
  $cyan-color: #00C5FF;

  .box {
    padding: 0;

    margin: 15px;

    width: 560px;
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
    margin-top: 10px;

    font-size: 35px;
  }

  p {
    margin-left: $margin-left;
    margin-top: 0;

    font-size: 20px;
  }

  img {
    height: 50px;

    margin-right: 0;
  }

  .github-element {
    height: 6vh;
    justify-content: center;

    margin-top: 10px;
    margin-bottom: 10px;

    p {
      margin-top: 0;

      font-size: 35px;

      transform: translateY(35%);
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
    width: fit-content;

    img {
      margin-top: 5px;
      margin-bottom: 5px;

      float: right;

      margin-right: 8px;
      margin-left: 8px;
    }
  }

  #title-row {
    display: flex;
  }
</style>

<div class="animation">
  <div class="box">
    <div id="title-row">
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