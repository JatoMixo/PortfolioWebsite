<script>
  // Components
  import Project from "./components/Project.svelte";
  import ToolCard from "./components/ToolCard.svelte";
  import SocialMedia from "./components/SocialMedia.svelte";
  
  // Images
  import JatoMixoLogo from "./images/jatomixo/jatomixo_logo.png";
  import JatoMixoLogoCircle from "./images/jatomixo/jatomixo_circle.png";
  import SvelteLogo from "./images/tech/SvelteLogo.png"
  import CSLogo from "./images/tech/CSLogo.png"
  import CppLogo from "./images/tech/CppLogo.png";
  import PythonLogo from "./images/tech/PythonLogo.png";
  import RustLogo from "./images/tech/RustLogo.png";
  import LinuxLogo from "./images/tech/LinuxLogo.png";
  
  // Social Media
  import TwitterLogo from "./images/twitter-logo.svg";
  import GithubLinkLogo from "./images/github-logo-link.svg";

  // Window dimensions
  let windowWidth;
  const SMALL_SCREEN_WIDTH = 550;

  // Scroll animation
  import { onMount } from 'svelte';
  let elementsVisible = [];

  onMount(() => {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entrie) => {
        if (entrie.isIntersecting) {
          elementsVisible.push(entrie.target.id);
        } else {
          elementsVisible.pop(entrie.target.id);
        }

        elementsVisible = elementsVisible;
      });
    });

    const logoElement = document.querySelectorAll(".logo");
    logoElement.forEach((element) => observer.observe(element));

    const aboutElement = document.querySelector("#about-me-section");
    observer.observe(aboutElement);

    const toolsElement = document.querySelector("#tools-row");
    observer.observe(toolsElement);

    const projectsElement = document.querySelector("#project-section");
    observer.observe(projectsElement);

    return () => {
      observer.disconnect();
    }
  });
</script>

<style lang="scss">
  /* On Scroll Animation*/
  @keyframes scroll-animation {
    from {
      opacity: 0;
      filter: blur(5px);
      transform: translateX(-100%);
    }

    to {
      opacity: 1;
      filter: blur(0);
      transform: translateX(0);
    }
  }

  .on-scroll {
    animation-name: scroll-animation;
    animation-duration: 1s;
    animation-fill-mode: forwards;
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
    }

    h1 {
      margin-top: 1dvw;

      font-size: 5dvw;
      text-shadow: 0 0 5px white;
    }
  }

  #about-me {
    position: relative;

    float: right;

    background-color: $secondary-background-color;
    box-shadow: -10px 10px #121212;
    border-radius: 15px;

    $padding-lateral: 1dvw;
    padding-left: $padding-lateral;
    padding-right: $padding-lateral;

    color: #E6E6E6;

    font-size: calc(14px + 0.75dvw);
  }

  #social-media-row {
    display: flex;

    justify-items: center;
    align-items: center;

    margin-top: 1dvh;

    height: 5dvw;

    justify-content: center;
  }

  #social-media-about {
    margin-top: 20px;

    display: flex;
    justify-content: center;
  }

  #jatomixo-logo-links {
    display: flex;

    margin-left: auto;
    margin-right: auto;

    width: 15dvw;

    vertical-align: middle;
  }

  #about-me-section {
    margin-bottom: 10dvh;
  }

  #tools-row {
    display: flex;
    gap: 75px;

    flex-wrap: wrap;

    justify-content: center;

    margin-bottom: 10dvh;
  }

  .section-title {
    text-align: center;
  }

  #logo-with-links {
    justify-content: center;
  }

  #project-section {
    display: flex;

    flex-wrap: wrap;
    gap: 30px;

    justify-content: center;
  }
</style>

<!-- Get data from window -->
<svelte:window bind:innerWidth={windowWidth}/>

<!--Title/Logo-->
<div class="center-container" id="logo">
  <div class="logo" class:on-scroll={elementsVisible.includes('logo')}>
    <img src={JatoMixoLogo} alt="Didn't load correctly"/>
    <h1>JatoMixo</h1>
  </div>
</div>

<!-- Question Box and Social Media -->
<div id="about-me-section" class="row" class:on-scroll={elementsVisible.includes("about-me-section")}>

  {#if windowWidth > SMALL_SCREEN_WIDTH}
    <div id="logo-with-links">
      <img src={JatoMixoLogoCircle} alt="JatoMixo" id="jatomixo-logo-links"/>

      <div id="social-media-row">
        <SocialMedia link="https://github.com/JatoMixo" image={GithubLinkLogo} image_alt="GitHub"/>
        <SocialMedia link="https://twitter.com/JatoMixo_Gamer" image={TwitterLogo} image_alt="Twitter"/>
      </div>
    </div>
  {/if}

  <div id="about-me">
    <div class="row">
      <h1>About me</h1>

      {#if windowWidth <= SMALL_SCREEN_WIDTH && windowWidth >= 320}
        <div id="social-media-about">
          <SocialMedia link="https://github.com/JatoMixo" image={GithubLinkLogo} image_alt="GitHub"/>
          <SocialMedia link="https://twitter.com/JatoMixo_Gamer" image={TwitterLogo} image_alt="Twitter"/>
        </div>
      {/if}
    </div>
    <p>Hello! I'm <span class="blue-flash">JatoMixo</span>, a <span class="green-flash">High-School student</span> who loves <span class="yellow-flash">programming</span> stuff.</p>

    <p>Right now (2023), I'm 15 years old and I started coding small games on <span class="cyan-flash">Unity</span> back when I was 13.
      From that point, I started learning and looking into several programming areas like <span class="dark-green-flash">Web Development</span> or <span class="purple-flash">Low-Level Systems Programming</span>. 
    </p>

    <p>Right now, I'm trying to learn <span class="red-flash">Embedded Rust</span> by attending to some katas in my town.</p>
  </div>
</div>

<h1 class="section-title" id="tools-identifier" class:on-scroll={elementsVisible.includes("tools-row")}>My Tools</h1>

<div id="tools-row" class:on-scroll={elementsVisible.includes("tools-row")}>
  <div class="toolcard">
    <ToolCard image={CSLogo} name="C#" description="I have made several C# projects in the past using the .NET framework and it was the lenguage I started with."/>
  </div>
  <div class="toolcard">
    <ToolCard image={SvelteLogo} name="Svelte" description="This website was made using Svelte! It was my first time using a JS framework and the result isn't that bad... or is it?"/>
  </div> 
  <div class="toolcard">
    <ToolCard image={RustLogo} name="Rust" description="I'm learning Rust with the Rust Book made by O'Reilly and I'm also doing some projects with ESP32S2s to learn Embedded Rust."/>
  </div>
  <div class="toolcard">
    <ToolCard image={PythonLogo} name="Python" description="I have worked with Python and Raspberry Pi's in the past to make some automatas and they haven't failed yet, so that's a win."/>
  </div>
  <div class="toolcard">
    <ToolCard image={LinuxLogo} name="Linux" description="In 2022, I started learning about Linux and I have some experience personalizing Debian-based distros. Also, I use Kali Linux."/>
  </div>
</div>

<h1 class="section-title" id="projects-identifier" class:on-scroll={elementsVisible.includes("project-section")}>My Projects</h1>

<div id="project-section" class:on-scroll={elementsVisible.includes("project-section")}>
  <Project title="My Website" description="The website you're currently watching" tool={SvelteLogo} github="https://github.com/JatoMixo/PortfolioWebsite"/>
  <Project title="AOC 2022" description="The problems I solved from Advent Of Code 2022" tool={PythonLogo} github="https://github.com/JatoMixo/AdventOfCode2022"/>
  <Project title="Text Encrypter" description="Encrypt or decrypt text in 5 different ways" tool={PythonLogo} github="https://github.com/JatoMixo/PythonEncrypter"/>
  <Project title="WH-Automata" description="An automata for the water heater in my house" tool={PythonLogo} github="https://github.com/JatoMixo/Automata-Calentador"/>
  <Project title="Polynominal Calc" description="Unfinished program for polynominal operations" tool={CppLogo} github="https://github.com/JatoMixo/PolynominalCalculator"/>
  <Project title="Keypad Controller" description="Rust Code to control a Keypad with ESP32S2" tool={RustLogo} github="https://github.com/JatoMixo/keypad-aindustriosa"/>
</div>