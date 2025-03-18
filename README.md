<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 19th Birthday</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center; /* Center items vertically */
            flex-direction: column;
            font-family: Arial, sans-serif;
            background: rgb(228, 148, 228);
            min-height: 100vh;
            overflow-y: auto; /* Allow vertical scrolling */
            overflow-x: hidden; /* Prevent horizontal scroll */
            padding: 20px;
        }
        .cake {
            position: relative;
            width: 200px;
            height: 120px;
            background: #4d2600;
            border-radius: 10px;
            box-shadow: 0px 5px 15px rgba(0,0,0,0.3);
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            margin: 100px 0; /* Space above and below the cake */
        }
        .layer-top {
            width: 120px;
            height: 50px;
            background: #663300;
            position: absolute;
            top: -25px;
            border-radius: 10px;
        }
        .icing {
            position: absolute;
            width: 200px;
            height: 30px;
            background: #8b4513;
            top: -15px;
            border-radius: 10px;
            clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 75% 90%, 50% 100%, 25% 90%, 0% 100%);
        }
        .candle-number {
            position: absolute;
            top: -80px;
            font-size: 50px;
            font-weight: bold;
            color: gold;
            text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
            display: flex;
            gap: 5px;
            cursor: pointer; /* Change cursor to pointer */
        }
        .flame {
            position: absolute;
            width: 8px;
            height: 14px;
            background: orange;
            border-radius: 50%;
            animation: flicker 0.2s infinite alternate;
        }
        .flame.one { left: 5px; top: -15px; }
        .flame.nine { left: 27px; top: -15px; }
        @keyframes flicker {
            0% { transform: scale(1); opacity: 0.8; }
            100% { transform: scale(1.2); opacity: 1; }
        }
        .giftbox {
            position: relative; /* Changed to relative for proper stacking */
            width: 200px;
            height: 150px;
            cursor: pointer;
            transition: transform 0.3s ease-in-out;
            margin: 20px 0; /* Space above and below the gift box */
        }
        .giftbox:hover {
            transform: translateY(-10px);
        }
        .giftbox > div {
            position: absolute;
        }
        .giftbox .cover {
            width: 100%;
            height: 25%;
            background: #34495e;
            top: 0;
            left: 0;
            transition: transform 0.5s ease-in-out;
        }
        .giftbox .box {
            width: 100%;
            height: 80%;
            background: #2c3e50;
            bottom: 0;
        }
        .hidden-message {
            position: absolute;
            top: 49%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 20px;
            font-weight: bold;
            color: white;
            text-align: center;
            opacity: 0;
            transition: opacity 0.5s ease-in-out;
        }
        .envelope {
            width: 150px; /* Adjusted width */
            height: 100px; /* Adjusted height */
            background: #6a0dad;
            position: relative;
            cursor: pointer;
            border-radius: 5px;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.3);
            transform: rotate(-5deg);
            transition: transform 0.5s, box-shadow 0.3s;
            margin: 120px 0; /* Space above and below the envelope */
        }
        .envelope:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.5);
        }
        .envelope:before {
            content: "";
            position: absolute;
            top: -40px; /* Adjusted for smaller envelope */
            width: 0;
            height: 0;
            border-left: 60px solid transparent; /* Adjusted for smaller envelope */
            border-right: 60px solid transparent; /* Adjusted for smaller envelope */
            border-bottom: 40px solid #8c53b6; /* Adjusted for smaller envelope */
            transition: transform 0.5s;
        }
        .letter {
            display: none; /* Initially hidden */
            position: absolute;
            width: 250px;
            padding: 20px;
            background: #fdf6e3;
            border-radius: 10px;
            box-shadow: 5px 5px 15px rgba(0,0,0,0.3);
            text-align: center;
            font-size: 9px;
            font-family: 'Courier New', monospace;
            line-height: 1.5;
            border: 1px solid #d1bfa3;
            transform: rotate(-3deg);
            animation: fadeIn 0.5s ease-in-out;
            margin-top: 20px;
            background: linear-gradient(white, #f8e8c0);
        }
        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(-20px); }
            100% { opacity: 1; transform: translateY(0); }
        }
       
        .ribbon {
            position: absolute;
            width: 100%;
            height: 20px;
            background: red;
            top: 25%;
        }
        .ribbon::before, .ribbon::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background: red;
            border-radius: 50%;
        }
        .ribbon::before {
            left: -10px;
        }
        .ribbon::after {
            right: -10px;
        }
        .balloon {
            position: absolute;
            width: 40px;
            height: 60px;
            background: red;
            border-radius: 50%;
            animation: rise 4s linear forwards; /* Change to forwards to keep the balloon at the top */
        }
        @keyframes rise {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-100vh); opacity: 0; }
        }
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            animation: fall 3s linear infinite;
        }
        @keyframes fall {
            0% { transform: translateY(-10px); opacity: 1; }
            100% { transform: translateY(100vh); opacity: 0; }
        }
        /* Button Styles */
        .click-me-button {
            margin-top: 20px; /* Space above the button */
            padding: 10px 20px;
            font-size: 18px;
            color: white;
            background-color: #c431d4; /* Bootstrap primary color */
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .click-me-button:hover {
            background-color: #7f2681; /* Darker shade on hover */
        }

        /* Responsive Styles */
        @media (max-width: 600px) {
            .cake {
                width: 150px;
                height: 100px;
            }
            .layer-top {
                width: 90px;
                height: 40px;
            }
            .candle-number {
                font-size: 30px;
            }
            .giftbox {
                width: 150px;
                height: 120px;
            }
            .envelope {
                width: 120px; /* Adjusted width for smaller envelope */
                height: 80px; /* Adjusted height for smaller envelope */
            }
            .letter {
                width: 200px;
            }
            .click-me-button {
                font-size: 16px;
                padding: 8px 16px;
            }
        }
    </style>
</head>
<body>
    <div class="cake">
        <div class="layer-top"></div>
        <div class="icing"></div>
        <div class="candle-number" onclick="turnOffFlame()">
            1<div class="flame one" id="flameOne"></div>9<div class="flame nine" id="flameNine"></div>
        </div>
    </div>
    
    <div class="giftbox" onclick="openGift()">
        <div class="cover" id="giftCover"></div>
        <div class="box"></div>
        <div class="ribbon"></div>
    </div>
    
    <div class="envelope" onclick="openLetter()">
        <div class="flap" id="flap"></div>
        <div class="letter" id="letter">My Love, <br> Happiest Birthday, bb! I love you always. I hope ma appreciate nimo ni ako simple gift for you :)
            Thank you for coming into my life bb, always grateful ko na nakaila tika, gi hatag ka ni Lord sa akoa ug syempre akong naging first uyab hehe. 
            Happy unta ka now sa imo birthday, despite na busy ka sa imo acads bb and usahay ma-mroblema ka about ana. Unta kalimtan sa nimo kadali na and i enjoy nimo karon na day.
            Thank you sa tanan tanan lablab, sa imong love ug care. Grabe labs, super thankful jud ko na ikaw akong naging first uyab, no cap. 
            Hoping and praying na unta labs hantud2 ning atoa. Unta if mo abot sa time nga grabe tag away, ma-busy or unsa pana labs, pilion gihapon unta nato ang isa't isa. Love youuuu super bb.
            Unta labs if mo abot ang time na mag graduate nata, kita pa unta gihapon. Pero bitaw labs, grabe ka independent nimo and I really admire you from that.
            Very strong woman, kuyaw pud kung masuko hehe. Sorry bb if naa man ko sala or nabuhat na wala ko naka ingon ug sorry.  To be honest, wa jud ko kabalo labs unsa ako ibutang diri sa letter
            Basta kani akong ginapang ingon kay gikan sakong heart yieeee HAHAHAHHAA. Sorry bb if kiat kayko sahay ug sunggogan, rakag naay manghud niya mas tigulang pako nimo diay labs no hehe.
            I love you always lablab, miss youu. Love youuu so muchhh. I love youuu super superrr. Once again, Happy Birthday, Labidabidabs 💜😘
        </div>
    </div>
    
    <div class="hidden-message" id="hiddenMessage">Surprise!<br> Happy Birthday, My love <3</div>
    
    <!-- Click Me Buttons -->
    <button class="click-me-button" onclick="playYouTube()">Click Me!</button>
   
    <script>
        function playYouTube() {
            window.open("https://www.youtube.com/watch?v=0SqtBZNwF0M&t=71s", "_blank");
        }
        
        let giftOpen = false; // Track the state of the gift box
    
        function openGift() {
            const giftCover = document.getElementById("giftCover");
            const hiddenMessage = document.getElementById("hiddenMessage");
    
            if (!giftOpen) {
                // Open the gift
                giftCover.style.transform = "translateY(-80px)";
                hiddenMessage.style.opacity = "1";
                giftOpen = true;
    
                // Create balloons and confetti
                for (let i = 0; i < 30; i++) {
                    let balloon = document.createElement("div");
                    balloon.className = "balloon";
                    balloon.style.left = `${Math.random() * 100}%`;
                    balloon.style.top = `${Math.random() * 80}vh`; // Random vertical position
                    balloon.style.background = ["red", "blue", "green", "yellow"][Math.floor(Math.random() * 4)];
                    balloon.style.transform = `rotate(${Math.random() * 360}deg)`; // Random rotation
                    document.body.appendChild(balloon);
                    
                    let confetti = document.createElement("div");
                    confetti.className = "confetti";
                    confetti.style.left = `${Math.random() * 100}%`;
                    confetti.style.top = `${Math.random() * 80}vh`; // Random vertical position
                    confetti.style.background = ["pink", "purple", "orange", "cyan"][Math.floor(Math.random() * 4)];
                    document.body.appendChild(confetti);
                }
            } else {
                // Close the gift
                giftCover.style.transform = "translateY(0)";
                hiddenMessage.style.opacity = "0";
                giftOpen = false;
    
                // Remove balloons and confetti
                const balloons = document.querySelectorAll('.balloon');
                const confettis = document.querySelectorAll('.confetti');
                balloons.forEach(balloon => balloon.remove());
                confettis.forEach(confetti => confetti.remove());
            }
        }
    
        function openLetter() {
            let letter = document.getElementById("letter");
            let envelope = document.querySelector(".envelope");
            
            if (letter.style.display === "none" || letter.style.display === "") {
                letter.style.display = "block";
                letter.style.opacity = "1"; // Ensure the letter is visible
                envelope.style.transform = "rotate(0deg) scale(1.2)";
            } else {
                letter.style.display = "none";
                letter.style.opacity = "0"; // Hide the letter
                envelope.style.transform = "rotate(-5deg) scale(1)";
            }
        }
    
        function turnOffFlame() {
            const flameOne = document.getElementById("flameOne");
            const flameNine = document.getElementById("flameNine");
            flameOne.style.display = "none"; // Hide the first candle flame
            flameNine.style.display = "none"; // Hide the second candle flame
        }

        function showBalloon(event) {
            const balloon = document.createElement("div");
            balloon.className = "balloon";
            balloon.style.left = `${event.clientX - 20}px`; // Center the balloon on click
            balloon.style.top = `${event.clientY - 60}px`; // Position above the click
            document.body.appendChild(balloon);

            // Remove the balloon after the animation
            setTimeout(() => {
                balloon.remove();
            }, 4000); // Adjust time to match the animation duration
        }
    </script>
</body>
</html>
