<script>
    let value2 = 0;
    let selectedAnswer = ""; // Store the selected answer

    function checkGuess2() {
        const resultBox = document.getElementById('result-2');
        const extraBox2 = document.getElementById('extra-box2');

        if (value2 >= 81000 && value2 <= 85000) {
            resultBox.textContent = "Gut geschätzt! 83 640 PKW";
            resultBox.style.color = "#9cbb50";
            extraBox2.style.display = "block";
        } else if (value2 >= 78000 && value2 <= 87000) {
            resultBox.textContent = "Fast";
            resultBox.style.color = "orange";
            extraBox2.style.display = "none";
        } else {
            resultBox.textContent = "Probiers nochmal";
            resultBox.style.color = "#e46767";
            extraBox2.style.display = "none";
        }
    }

    function checkAnswer(answer) {
        selectedAnswer = answer; // Store the selected answer
    }
</script>

<div class="text-box2">
    <p>Wie viele PKW verursachen in <b>24 Stunden</b> genauso viel <b>Kohlendioxid </b> wie ein Kreuzfahrtschiff in derselben Zeit?</p>
</div>

<div class="slider2">
    <input
        id="slider2"
        type="range"
        min="0"
        max="100000"
        step="100"
        on:mouseup={checkGuess2}
        on:keyup={checkGuess2}
        bind:value={value2}
    />
    <label for="slider2"> {value2} </label>

    <div class="pictograms">
        {#each Array(Math.floor(value2 / 1000)) as _}
            <img src="car4.png" alt="Car" width="20" />
        {/each}
    

  </div> 

 

    <p style="font-size: 12px; margin-top: 12px;">

 
     Ein Auto = 1 Millionen PKW
     
    </p>


</div>

<div id="result-2" class="result-box-2"></div>

<div id="extra-box2" class="extra-box2" style="display: none;">
    <p>
        Ein Kreuzfahrtschiff stößt also am Tag sehr viel mehr Schadstoffe aus als ein Auto.
    </p>
</div>

<style>
    :global(body) {
        background-color: #efe0cd; /* Beige background */
        margin: 0; /* Remove default body margin */
        color: #427fb7; /* Blue text */
        font-family; PT Serif:
        font-size: 18px;
    }
    
    div {
        
        padding: 10px;
    }

    .text-box2 {
        padding: 18px;
        border-radius: 15px;
        margin: 30px;
    }

    .slider2 {
        margin: 30px;
        color: #427fb7; /* Blue text on slider */
    }

    .result-box-2 {
        font-size: 1.2em;
        font-weight: bold;
        text-align: center;
        margin-top: 20px;
    }

    .extra-box2 {
        font-size: 1em;
        color: #427fb7; /* Blue text */
        text-align: justify;
        background-color: #e9ffe9;
        border-radius: 10px;
        padding: 15px;
        margin: 20px 30px;
    }

    input[type="range"] {
        margin-top: 10px;
        width: 100%;
    }

    .pictograms {
        display: flex;
        flex-wrap: wrap;
    }

    .pictograms img {
        margin: 2px;
    }
</style>
