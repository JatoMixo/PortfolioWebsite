<script>
  // Components
  import Project from "./components/Project.svelte";
  import ToolCard from "./components/ToolCard.svelte";
  import Terminal from "./components/Terminal.svelte";
  
  // Images
  import JatoMixoLogo from "./images/jatomixo/jatomixo_logo.png";
  import GithubLogo from "./images/tech/GithubLogo.png";
  import SvelteLogo from "./images/tech/SvelteLogo.png"
  import CSLogo from "./images/tech/CSLogo.png"
  import UnityLogo from "./images/tech/UnityLogo.png"
  import PythonLogo from "./images/tech/PythonLogo.png";
  import RustLogo from "./images/tech/RustLogo.png";
  import LinuxLogo from "./images/tech/LinuxLogo.png";
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
      width: 57.5dvw;

      margin-top: 2dvh;

      animation-name: flash-animation;
      animation-duration: 500ms;
    }

    h1 {
      margin-top: 2dvh;
      margin-bottom: 2dvh;

      font-size: 6dvw;
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

<div class="row">
  <ToolCard image={CSLogo} description="Something." name="Something"/>
  <ToolCard image={LinuxLogo} name="Linux" description="Best OS ever"/>
  <ToolCard image={PythonLogo} name="Python" description="Decent language"/>
  <ToolCard image={RustLogo} name="Rust" description="Amazing language"/>
  <ToolCard image={SvelteLogo} name="Svelte" description="Best JS framerok"/>
  <ToolCard image={UnityLogo} name="Unity" description="Shit I used 2 years ago"/>
</div>
<hr>

<Terminal/>

<hr>

<Project name="Website" tool={SvelteLogo} description="A website." github="https://github.com/JatoMixo/PortfolioWebsite"/>
<Project name="Water-Heater Automata" tool={GithubLogo} description="An automata for a water heater" github="https://github.com/JatoMixo/Automata-Calentador"/>