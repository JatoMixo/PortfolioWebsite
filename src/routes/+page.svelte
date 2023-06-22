<script>
  // Components
  import Project from "./components/Project.svelte";
  import ToolCard from "./components/ToolCard.svelte";
  import Terminal from "./components/Terminal.svelte";
  import QuestionBox from "./components/QuestionBox.svelte";
  
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

  .center-container {
    margin-top: 2dvw;

    display: table;
    height: 100%;
    width: 100%;
  }

  .logo {
    height: 100dvh;

    display: table-cell;
    vertical-align: middle;

    transform-origin: center;

    text-align: center;

    img {
      width: 60dvw;

      animation-name: flash-animation;
      animation-duration: 500ms;
    }

    h1 {
      margin-top: 1dvw;

      font-size: 5dvw;
      text-shadow: 0 0 5px white;
    }
  }
</style>

<!--Title/Logo-->
<div class="center-container">
  <div class="logo">
    <img src={JatoMixoLogo} alt="Didn't load correctly"/>
    <h1>JatoMixo</h1>
  </div>
</div>

<QuestionBox/>

<!--<div class="row">
  <ToolCard image={CSLogo} name="C#" description="I have made several C# projects in the past using the .NET framework and it was the lenguage I started with."/>
  <ToolCard image={SvelteLogo} name="Svelte" description="This website was made using Svelte! It was my first time using a JS framework and the result isn't that bad... or is it?"/>
  <ToolCard image={PythonLogo} name="Python" description="I have worked with Python and Raspberry Pi's in the past to make some automatas and they haven't failed yet, so that's a win."/>
  <ToolCard image={RustLogo} name="Rust" description="I'm learning Rust with the Rust Book made by O'Reilly and I'm also doing some projects with ESP32S2s to learn Embedded Rust"/>
  <ToolCard image={UnityLogo} name="Unity" description="Making games was the first thing I wanted to do, and so, I learnt Unity before anything else."/>
  <ToolCard image={LinuxLogo} name="Linux" description="In 2022, I started learning about Linux and I have some experience personalizing Debian-based distros. Also, I use Kali Linux."/>
</div>-->