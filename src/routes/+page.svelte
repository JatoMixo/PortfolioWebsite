<script>
  // Components
  import Project from "./components/Project.svelte";
  import ToolCard from "./components/ToolCard.svelte";
  import Terminal from "./components/Terminal.svelte";
  
  // Images
  import JatoMixoLogo from "./images/jatomixo/jatomixo_logo.png";
  import GithubLogo from "./images/GithubLogo.png";
</script>

<style lang="scss">
  @keyframes flash-animation {
    from {
      opacity: 0%;
    }
    to {
      opacity: 100%;
    }
  }
  .logo {
    transform-origin: center;
    justify-content: center;

    text-align: center;

    position: relative;

    img {
      width: 60%;

      animation-name: flash-animation;
      animation-duration: 500ms;
    }

    h1 {
      margin-top: 3vw;
      margin-bottom: 3vw;

      font-size: 6vw;
      text-shadow: 0 0 5px white;
    }
  }
</style>

<!--Title/Logo-->
<div class="logo">
  <img src={JatoMixoLogo} alt="Didn't load correctly"/>
  <h1>JatoMixo</h1>
</div>

<hr>

<!--About-->
<h1>About</h1>

<ToolCard img="" description="Something." name="Something"/>

<hr>

<Terminal/>

<hr>

<Project name="Website" tool={GithubLogo} description="A website." github="https://github.com/JatoMixo/PortfolioWebsite"/>