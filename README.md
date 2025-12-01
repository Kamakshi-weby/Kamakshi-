
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kamakshi Edits</title>

<style>
    body {
        margin: 0;
        font-family: "Poppins", sans-serif;
        background: #f7eefe;
        color: #333;
    }

    header {
        text-align: center;
        padding: 40px 20px;
        background: #e9d4ff;
        border-bottom: 3px solid #c9a7ff;
    }

    h1 {
        font-size: 2.6rem;
        margin: 0;
        font-weight: 800;
    }

    .subtitle {
        font-size: 1.2rem;
        opacity: 0.8;
        margin-top: 8px;
    }

    .container {
        max-width: 850px;
        margin: 40px auto;
        padding: 30px;
    }

    .section-title {
        font-size: 1.6rem;
        font-weight: 700;
        margin-bottom: 20px;
    }

    /* CARD STYLE */
    .card-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
        gap: 20px;
        margin-bottom: 40px;
    }

    .card {
        background: white;
        border-radius: 18px;
        padding: 20px;
        text-align: center;
        border: 2px dashed #d3baff;
        cursor: pointer;
        transition: 0.25s;
        box-shadow: 0 4px 12px rgba(0,0,0,0.08);
        position: relative;
    }

    .card:hover {
        transform: translateY(-5px);
        border-color: #b28aff;
    }

    .card img {
        width: 60px;
        margin-bottom: 10px;
        opacity: 0.85;
    }

    .card.selected {
        background: #ecdfff;
        border-color: #9d70ff;
        box-shadow: 0 0 15px rgba(157,112,255,0.5);
    }

    textarea, input {
        width: 100%;
        padding: 14px;
        font-size: 1rem;
        border: 2px solid #d3baff;
        border-radius: 12px;
        background: #fff;
        margin-bottom: 20px;
    }

    button {
        background: #b28aff;
        color: white;
        padding: 14px 26px;
        border-radius: 12px;
        border: none;
        font-size: 1.1rem;
        cursor: pointer;
        transition: 0.2s;
        font-weight: 600;
    }

    button:hover {
        background: #9c6aff;
    }
</style>
</head>

<body>

<header>
    <h1>Kamakshi Edits</h1>
    <p class="subtitle">Aesthetic Editing • Ads • Photos • Videos • Websites</p>
</header>

<div class="container">

    <!-- SECTION 1 -->
    <div class="section-title">Who Are You?</div>
    <div class="card-grid" id="userType">
        <div class="card" data-value="Business Owner">
            <img src="https://i.imgur.com/HYzI3J6.png">
            Business Owner
        </div>
        <div class="card" data-value="Creator">
            <img src="https://i.imgur.com/4jz5PwM.png">
            Creator
        </div>
        <div class="card" data-value="Brand">
            <img src="https://i.imgur.com/wuLzF2n.png">
            Brand
        </div>
        <div class="card" data-value="Influencer">
            <img src="https://i.imgur.com/F7tXO80.png">
            Influencer
        </div>
    </div>

    <!-- SECTION 2 -->
    <div class="section-title">What Work Do You Want?</div>
    <div class="card-grid" id="workType">
        <div class="card" data-value="Photo Editing">
            <img src="https://i.imgur.com/zmbYwSW.png">
            Photo Editing
        </div>
        <div class="card" data-value="Video Editing">
            <img src="https://i.imgur.com/HYzI3J6.png">
            Video Editing
        </div>
        <div class="card" data-value="Ad Editing">
            <img src="https://i.imgur.com/XyS8zmC.png">
            Ad Editing
        </div>
        <div class="card" data-value="Website Creation">
            <img src="https://i.imgur.com/NBfQx7P.png">
            Website Creation
        </div>
        <div class="card" data-value="Brand Content">
            <img src="https://i.imgur.com/8Vh2fDs.png">
            Brand Content
        </div>
    </div>

    <!-- DESCRIPTION -->
    <div class="section-title">Describe What You Need</div>
    <textarea id="details" rows="6" placeholder="Explain your exact requirements here..."></textarea>

    <!-- SEPARATE SOCIAL MEDIA HANDLING SECTION -->
    <div class="section-title">Do You Want Social Media Handling?</div>

    <div class="card-grid" id="socials">
        <div class="card" data-value="Yes">
            <img src="https://i.imgur.com/42nZ2tb.png">
            Yes
        </div>
        <div class="card" data-value="No">
            <img src="https://i.imgur.com/0mpbO9v.png">
            No
        </div>
        <div class="card" data-value="Maybe">
            <img src="https://i.imgur.com/QgmIFq2.png">
            Maybe
        </div>
    </div>

    <input type="text" id="budget" placeholder="If Yes, what's your budget? (optional)">

    <!-- SEND BUTTON -->
    <button onclick="sendMail()">Send Request</button>

</div>

<script>
function enableSelection(sectionId) {
    const cards = document.querySelectorAll(`#${sectionId} .card`);
    cards.forEach(card => {
        card.addEventListener("click", () => {
            cards.forEach(c => c.classList.remove("selected"));
            card.classList.add("selected");
        });
    });
}

enableSelection("userType");
enableSelection("workType");
enableSelection("socials");

function sendMail() {
    let user = document.querySelector("#userType .selected");
    let work = document.querySelector("#workType .selected");
    let social = document.querySelector("#socials .selected");
    let details = document.getElementById("details").value;
    let budget = document.getElementById("budget").value;

    if (!user || !work || details.trim() === "") {
        alert("Please fill out all required fields.");
        return;
    }

    let body =
        "Who Are They: " + user.dataset.value + "%0D%0A" +
        "Work Needed: " + work.dataset.value + "%0D%0A" +
        "Details: " + details + "%0D%0A" +
        "Social Media Handling: " + (social ? social.dataset.value : "Not selected") + "%0D%0A" +
        "Budget: " + budget;

    window.location.href = "mailto:kamakshisinghranchi1@gmail.com"
        + "?subject=New Client Request"
        + "&body=" + body;
}
</script>

</body>
</html>
