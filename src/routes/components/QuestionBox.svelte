<script>

    let actual_question = "";

    const questions = {
        "Why did you learn to code": "Mainly, because I wanted to make my own games, and that's the reason I started with Unity",
        "How did you start learning": "I started by watching programming tutorials on youtube and started making projects as soon as I could",
    };

    function changeQuestion(newQuestion) {
        actual_question = newQuestion;

        console.log(actual_question);
    }
</script>

<style lang="scss">
    p {
        margin: 0px;
    }

    #main-box {
        position: relative;

        height: 30dvh;
        width: 63dvw;
    }

    #questions-section {

        position: absolute;
        bottom: 0;

        margin-bottom: 1.5dvh;
    }

    .question-button {
        $background-color: #1f1f1f;

        background-color: $background-color;
        border-radius: 5px;
        border: solid 5px $background-color;

        margin-top: 5px;

        transition: background-color 0.1s, border-color 0.1s;
    }

    .question-button:hover {
        $new-background-color: #4f4f4f;

        background-color: $new-background-color;
        border-color: $new-background-color;
    }

    .question-title {
        margin-bottom: 2dvh;

        font-size: 150%;
        color: white;
        text-shadow: 0 0 10px whtie;
    }

    .question-body {
        color: #cccccc;
    }
</style>

<div class="box" id="main-box">

    {#if actual_question == ""}
        <p>Hello! I'm <span class="blue-flash">JatoMixo</span>, a High School Student who loves <span class="yellow-flash">programming</span> stuff</p>
        <p>Click on the <span class="green-flash">questions</span> below to know more about me.</p>
    {:else}
        <p class="question-title">{actual_question}</p>
        <p class="question-body">{questions[actual_question]}</p>
    {/if}

    <div id="questions-section">
        {#each Object.keys(questions) as question}
            <button class="question-button" on:click={() => changeQuestion(question)}>{question}</button>
        {/each}
    </div>
</div>