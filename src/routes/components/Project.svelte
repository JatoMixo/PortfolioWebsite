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

        width: 500px;
    }

    #title-row {
        display: flex;

        align-content: center;
        vertical-align: middle;
    }

    #title {
        margin: $margin;
        margin-top: 7px;

        font-size: 45px;

        vertical-align: middle;
    }

    #description-paragraph {
        margin: $margin;
        font-size: 30px;     
    }

    #tool-box {
        padding: 5px;

        margin: -5px;
    }

    #image-tool {
        width: 60px;

        margin: 0;

        vertical-align: middle;
    }

    #github-logo {
        height: 70px;

        vertical-align: middle;
    }

    #github-link {
        display: flex;

        align-content: center;
        vertical-align: middle;

        color: whitesmoke;
        text-decoration: none;

        font-size: 20px;
        text-align: center;
    }
</style>

< class="box" id="main-box">
    <div id="title-row">
        <h1 id="title">{title}</h1>

        <div id="tool-box" class="box">
            <img src={tool} alt="Tool" id="image-tool"/>
        </div>
    </div>

    <p id="description-paragraph">{description}</p>

    <hr>

    <a href={github} target="_blank" id="github-link">
        <img src={GithubLogo} alt="" id="github-logo"/>
        <h1 id="github-text">GitHub</h1>
    </a>
</div>