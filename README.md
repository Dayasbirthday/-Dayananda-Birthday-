<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday, Daya!</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="welcome-page">
        <div class="confetti"></div>
        <h1 class="greeting">Happy Birthday, Daya!</h1>
        <div class="hero-image">
            <img src="daya_photo.jpg" alt="Daya" class="profile-image">
            <p class="subtext">Celebrating the awesome, one-of-a-kind Daya!</p>
        </div>
        <div class="countdown">Only <span id="countdown-timer">xx Days, xx Hours</span> Until the Celebration Begins!</div>
        <div class="nav-buttons">
            <button onclick="enterParty()">Enter the Party!</button>
            <button onclick="viewMessages()">Birthday Messages</button>
        </div>
        <p class="quote">“Friends are the family we choose. Here’s to Daya, our chosen family!”</p>
    </div>

    <script src="script.js"></script>
</body>
</html>
body, html {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: Arial, sans-serif;
    background: linear-gradient(to bottom right, orange, purple);
    overflow: hidden;
}

.welcome-page {
    text-align: center;
    color: white;
}

.greeting {
    font-size: 3em;
    font-weight: bold;
    margin: 20px 0;
    animation: glow 1s ease-in-out infinite alternate;
}

@keyframes glow {
    from { text-shadow: 0 0 10px white; }
    to { text-shadow: 0 0 20px yellow; }
}

.hero-image {
    margin: 20px 0;
}

.profile-image {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    border: 4px solid white;
    box-shadow: 0 0 20px white;
}

.subtext {
    font-size: 1.2em;
    margin-top: 10px;
}

.countdown {
    font-size: 1.5em;
    margin: 20px 0;
}

.nav-buttons button {
    padding: 10px 20px;
    margin: 10px;
    font-size: 1.2em;
    border: none;
    border-radius: 10px;
    color: white;
    background-color: teal;
    cursor: pointer;
    transition: background-color 0.3s;
}

.nav-buttons button:hover {
    background-color: darkcyan;
}

.quote {
    font-style: italic;
    margin-top: 30px;
    font-size: 1.2em;
}

/* Confetti Animation - Placeholder */
.confetti {
    position: fixed;
    top: 0;
    width: 100%;
    height: 100%;
    background: url('confetti.gif') center/cover no-repeat; /* Add a confetti animation GIF here */
    pointer-events: none;
}
function startCountdown() {
    const eventDate = new Date("November 11, 2024 00:00:00").getTime();

    setInterval(() => {
        const now = new Date().getTime();
        const timeLeft = eventDate - now;

        const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
        const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));

        document.getElementById("countdown-timer").textContent = `${days} Days, ${hours} Hours`;
    }, 1000);
}

startCountdown();
function enterParty() {
    alert("Welcome to Daya’s Party Page!");
}

function viewMessages() {
    alert("See the heartfelt messages for Daya here!");
}
