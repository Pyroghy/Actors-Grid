<script lang="ts">
    const answers = [
        { a1: "Bryan Cranston", a2: "Ryan Gosling", a3: "Oscar Isaac" },
        { b1: "Bryan Cranston", b2: "Ryan Gosling", b3: "Oscar Isaac" },
        { c1: "Bryan Cranston", c2: "Ryan Gosling", c3: "Oscar Isaac" },
    ];

    function answerPrompt(e: any) {
        const answer = prompt("answer??");
        const tileId = e.target.id;
        const element = document.getElementById(tileId);

        if (tileId.startsWith("a")) {
            if (answer === answers[0][tileId]) {
                element.innerText = answers[0][tileId];
                element.style.backgroundColor = "lightGreen";
            } else {
                element.style.backgroundColor = "crimson";
            }
        } else if (tileId.startsWith("b")) {
            if (answer === answers[2][tileId]) {
                element.innerText = answers[0][tileId];
                element.style.backgroundColor = "lightGreen";
            } else {
                element.style.backgroundColor = "crimson";
            }
        } else if (tileId.startsWith("c")) {
            if (answer === answers[1][tileId]) {
                element.innerText = answers[0][tileId];
                element.style.backgroundColor = "lightGreen";
            } else {
                element.style.backgroundColor = "crimson";
            }
        }
    }
</script>

<main>
    <div class="grid">
        <div class="row">
            <div class="el">0</div>
            <div class="head el">Breaking Bad</div>
            <div class="head el">Blade Runner 2049</div>
            <div class="head el">Moon Knight</div>
        </div>

        <div class="row">
            <div class="head el">Drive</div>
            <button class="el" id="a1" on:click={answerPrompt}>0</button>
            <button class="el" id="a2" on:click={answerPrompt}>0</button>
            <button class="el" id="a3" on:click={answerPrompt}>0</button>
        </div>

        <div class="row">
            <div class="head el">Drive</div>
            <button class="el" id="b1" on:click={answerPrompt}>0</button>
            <button class="el" id="b2" on:click={answerPrompt}>0</button>
            <button class="el" id="b3" on:click={answerPrompt}>0</button>
        </div>

        <div class="row">
            <div class="head el">Drive</div>
            <button class="el" id="c1" on:click={answerPrompt}>0</button>
            <button class="el" id="c2" on:click={answerPrompt}>0</button>
            <button class="el" id="c3" on:click={answerPrompt}>0</button>
        </div>
    </div>
</main>

<style>
    main {
        display: block;
    }

    div.grid {
        display: flex;

        width: 80vw;
        height: 80vw;

        gap: 0.25rem;

        flex-direction: column;
    }

    div.row {
        display: flex;
        flex-direction: row;
        gap: 0.25rem;
    }

    button {
        margin: 0;
        padding: 0;
        border: none;
        cursor: pointer;

        border-radius: 0.5rem;
    }

    button:hover {
        background-color: grey;
    }

    .el {
        display: flex;
        place-items: center;
        place-content: center;

        width: calc((80vw - 0.75rem) / 4);
        height: calc((80vw - 0.75rem) / 4);
    }
</style>
