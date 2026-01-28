# SD1M2SKILLEindOpdrachtFetch
GRID.HTML
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Dashboard</title>

    <!-- Google Font: Bitcount Single -->
    <link href="https://fonts.googleapis.com/css2?family=Bitcount+Single&display=swap" rel="stylesheet">

    <link rel="stylesheet" href="style.css">
</head>
<body>

<header class="header">
    <h1>GRID compositie</h1>
</header>

<main class="dashboard">

    <section class="block fetch">
          <h2>Zoek een Pokémon</h2>

    <input
        type="text"
        id="pokemonName"
        placeholder="Bijv. pikachu"
    >

    <button onclick="fetchData()">Zoek Pokémon</button>

    <br><br>

    <img
        id="pokemonSprite"
        alt="Pokemon sprite"
        style="display: none;"
    >

    <script src="poke.js"></script>
    </section>

    <section class="block stopwatch">
    <h2>Stopwatch</h2>

    <div id="time">00:00:00</div>

    <div class="controls">
        <button id="startBtn">Start</button>
        <button id="pauseBtn">Pauze</button>
        <button id="resetBtn">Reset</button>
    </div>
   </section>


    <section class="block formulier">
                <section class="card">
            <h2>Contactformulier</h2>

            <form action="#" method="post" class="contact-form">

                <div class="form-group">
                    <label for="naam">Naam</label>
                    <input type="text" id="naam" name="naam" required>
                </div>

                <div class="form-group">
                    <label for="email">E-mailadres</label>
                    <input type="email" id="email" name="email" required>
                </div>

                <div class="form-group">
                    <label for="bericht">Bericht</label>
                    <textarea id="bericht" name="bericht" rows="3" required></textarea>
                </div>

                <div class="form-group">
                    <label>Geslacht</label>
                    <div class="options">
                        <label><input type="radio" name="geslacht" value="man"> Man</label>
                        <label><input type="radio" name="geslacht" value="vrouw"> Vrouw</label>
                    </div>
                </div>

                <div class="form-group checkbox">
                    <label>
                        <input type="checkbox" name="nieuwsbrief">
                        Inschrijven voor het overnemen van de wereld
                    </label>
                </div>

                <div class="form-group">
                    <label for="onderwerp">Onderwerp</label>
                    <select id="onderwerp" name="onderwerp">
                        <option value="vraag">Vraag</option>
                        <option value="feedback">Feedback</option>
                        <option value="klacht">Klacht</option>
                    </select>
                </div>

                <button type="submit" class="btn-submit">Versturen</button>

            </form>
        </section>

    </section>

</main>

<footer class="footer">
    <p>&copy; Grid opdracht</p>
</footer>
<!-- ik heb voor de timer ai gebruikt voor hulp -->
<script>
let startTime = 0;
let elapsedTime = 0;
let timerInterval = null;

const timeDisplay = document.getElementById("time");
const startBtn = document.getElementById("startBtn");
const pauseBtn = document.getElementById("pauseBtn");
const resetBtn = document.getElementById("resetBtn");

function formatTime(time) {
    const milliseconds = Math.floor((time % 1000) / 10);
    const seconds = Math.floor((time / 1000) % 60);
    const minutes = Math.floor((time / (1000 * 60)) % 60);

    return (
        String(minutes).padStart(2, "0") + ":" +
        String(seconds).padStart(2, "0") + ":" +
        String(milliseconds).padStart(2, "0")
    );
}

function startTimer() {
    if (timerInterval) return;

    startTime = Date.now() - elapsedTime;
    timerInterval = setInterval(() => {
        elapsedTime = Date.now() - startTime;
        timeDisplay.textContent = formatTime(elapsedTime);
    }, 10);
}

function pauseTimer() {
    clearInterval(timerInterval);
    timerInterval = null;
}

function resetTimer() {
    clearInterval(timerInterval);
    timerInterval = null;
    elapsedTime = 0;
    timeDisplay.textContent = "00:00:00";
}

startBtn.addEventListener("click", startTimer);
pauseBtn.addEventListener("click", pauseTimer);
resetBtn.addEventListener("click", resetTimer);
</script>
</body>
</html>

![skilleindopdracht](https://github.com/user-attachments/assets/fed22c20-8fd4-420a-850e-3f9560bf84df)
