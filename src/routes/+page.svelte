  <script>
  // Components
  import Project from "./components/Project.svelte";
  import ToolCard from "./components/ToolCard.svelte";
  import QuestionBox from "./components/QuestionBox.svelte";
  import SocialMedia from "./components/SocialMedia.svelte";
  
  // Images
  import JatoMixoLogo from "./images/jatomixo/jatomixo_logo.png";
  import JatoMixoLogoCircle from "./images/jatomixo/jatomixo_circle.png";
  import GithubLogo from "./images/tech/GithubLogo.png";
  import SvelteLogo from "./images/tech/SvelteLogo.png"
  import CSLogo from "./images/tech/CSLogo.png"
  import UnityLogo from "./images/tech/UnityLogo.png"
  import PythonLogo from "./images/tech/PythonLogo.png";
  import RustLogo from "./images/tech/RustLogo.png";
  import LinuxLogo from "./images/tech/LinuxLogo.png";
  
  // Social Media
  import TwitterLogo from "./images/twitter-logo.svg";
  import GithubLinkLogo from "./images/github-logo-link.svg";
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

  #jatomixo-logo-links {

  }

  #question-box-row {

  }

  #logo-with-links {

  }

  #social-media-row {

  }

  #question-box {
    float: right;

    width: fit-content;
    height: fit-content;
  }
</style>

<!--Title/Logo-->
<div class="center-container">
  <div class="logo">
    <img src={JatoMixoLogo} alt="Didn't load correctly"/>
    <h1>JatoMixo</h1>
  </div>
</div>

<!-- Question Box and Social Media -->
<div id="question-box-row" class="row">
  <div id="logo-with-links">
    <img src={JatoMixoLogoCircle} alt="JatoMixo" id="jatomixo-logo-links"/>

    <div id="social-media-row">
      <SocialMedia link="https://github.com/JatoMixo" image={GithubLinkLogo} image_alt="GitHub"/>
      <SocialMedia link="https://twitter.com/JatoMixo_Gamer" image={TwitterLogo} image_alt="Twitter"/>
    </div>
  </div>

  <div id="question-box">
    <QuestionBox/>
  </div>
</div>

<!--<div class="row">
  <ToolCard image={CSLogo} name="C#" description="I have made several C# projects in the past using the .NET framework and it was the lenguage I started with."/>
  <ToolCard image={SvelteLogo} name="Svelte" description="This website was made using Svelte! It was my first time using a JS framework and the result isn't that bad... or is it?"/>
  <ToolCard image={PythonLogo} name="Python" description="I have worked with Python and Raspberry Pi's in the past to make some automatas and they haven't failed yet, so that's a win."/>
  <ToolCard image={RustLogo} name="Rust" description="I'm learning Rust with the Rust Book made by O'Reilly and I'm also doing some projects with ESP32S2s to learn Embedded Rust"/>
  <ToolCard image={UnityLogo} name="Unity" description="Making games was the first thing I wanted to do, and so, I learnt Unity before anything else."/>
  <ToolCard image={LinuxLogo} name="Linux" description="In 2022, I started learning about Linux and I have some experience personalizing Debian-based distros. Also, I use Kali Linux."/>
</div>-->