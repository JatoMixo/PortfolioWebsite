<script>
    export let title = "";
    export let description = "";
    export let github = "";
    export let tool = "";

    import GithubLogo from "/src/routes/images/tech/GithubLogo.png";
</script>

<style lang="scss">

    $margin: 10px;

    #main-box {
        padding: 0;
        margin: 0;

        width: 550px;
    }

    #title-row {
        display: flex;

        align-content: center;
        vertical-align: middle;
    }

    #title {
        margin: $margin;
        margin-top: 7px;

        font-size: calc(25px + 1dvw);

        vertical-align: middle;
    }

    #description-paragraph {
        margin: $margin;
        font-size: calc(12px + 1dvw);     
    }

    #tool-box {
        padding: 5px;

        margin: -5px;

        display: block;
        margin-left: auto;
    }

    #image-tool {
        height: calc(30px + 1dvw);

        margin: 0;

        vertical-align: middle;
    }

    #github-logo {
        height: calc(50px + 1.5dvw);

        vertical-align: middle;
    }

    #github-link {
        width: 100%;
        height: 100%;

        align-content: center;
        vertical-align: middle;

        color: whitesmoke;
        text-decoration: none;

        font-size: calc(15px + 0.3dvw);
    }

    #link-elements {
        display: flex;
        vertical-align: middle;

        justify-content: center;

        gap: 20px;
    }

    #github-logo {
        vertical-align: middle;

        margin-top: 10px;
    }

    hr {
        margin: 0;
    }
</style>

<div class="box" id="main-box">
    <div id="title-row">
        <h1 id="title">{title}</h1>

        <div id="tool-box" class="box">
            <img src={tool} alt="Tool" id="image-tool"/>
        </div>
    </div>

    <p id="description-paragraph">{description}</p>

    <hr>

    <a href={github} target="_blank" id="github-link">
        <div id="link-elements">
            <img src={GithubLogo} alt="" id="github-logo"/>
            <h1 id="github-text">GitHub</h1>
        </div>
    </a>
</div>