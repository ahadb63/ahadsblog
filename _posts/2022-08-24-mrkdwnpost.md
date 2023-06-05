
<html>
<head>
    <title>NHL Standings Quiz</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start;
            height: 100vh;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
        }
        .quiz-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            position: sticky;
            top: 0;
            background-color: #f0f0f0;
            z-index: 1;
        }
        .team-button {
            padding: 20px;
            margin: 10px;
            font-size: 24px;
            cursor: pointer;
            border: none;
            background-color: #4CAF50;
            color: white;
            text-align: center;
            border-radius: 10px;
            transition: background-color 0.3s ease;
        }
        .team-button:hover {
            background-color: #45a049;
        }
        .standings-container {
            width: 200px;
            text-align: left;
            overflow-y: auto;
            height: calc(100vh - 100px);
            margin-top: 20px;
        }
        #feedback {
            color: red;
            font-weight: bold;
        }
        h1, h2 {
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <h1>NHL Standings Quiz</h1>
        <p id="team1" class="team-button" onclick="selectTeam(0)">Loading...</p>
        <p id="team2" class="team-button" onclick="selectTeam(1)">Loading...</p>
        <p id="feedback"></p>
    </div>
    <div class="standings-container">
        <h2>Standings:</h2>
        <ol id="standings"></ol>
    </div>

    <!-- the JavaScript part remains the same -->
</body>
</html>

<script>
        var standings = [
            'Boston',
            'Carolina',
            'New Jersey',
            'Toronto',
            'Vegas',
            'Edmonton',
            'Colorado',
            'Dallas',
            'NY Rangers',
            'Los Angeles',
            'Minnesota',
            'Seattle',
            'Tampa Bay',
            'Winnipeg',
            'NY Islanders',
            'Calgary',
            'Florida',
            'Nashville',
            'Pittsburgh',
            'Buffalo',
            'Ottawa',
            'Vancouver',
            'St Louis',
            'Detroit',
            'Washington',
            'Philadelphia',
            'Arizona',
            'Montréal',
            'San Jose',
            'Chicago',
            'Columbus',
            'Anaheim'
        ];
        var currentIndex = 0;
        var remainingTeams = [...standings];
        var correctIndex = 0;

        function loadTeams() {
            if (currentIndex < standings.length) {
                var randomWrongIndex = Math.floor(Math.random() * remainingTeams.length);

                correctIndex = Math.random() < 0.5 ? 0 : 1;

                document.getElementById("team" + (correctIndex + 1)).innerText = standings[currentIndex];
                document.getElementById("team" + ((correctIndex + 1) % 2 + 1)).innerText = remainingTeams[randomWrongIndex];
                document.getElementById("feedback").innerText = "";
            } else {
                alert("Quiz complete!");
            }
        }

        function selectTeam(index) {
            if (index === correctIndex) {
                var correctTeam = standings[currentIndex];

                // Remove the correct team from the remaining teams list.
                remainingTeams = remainingTeams.filter(function(team) {
                    return team !== correctTeam;
                });

                currentIndex += 1;
                loadTeams();
            } else {
                document.getElementById("feedback").innerText = "Try again!";
            }

            updateStandings();
        }

        function updateStandings() {
            var standingsList = document.getElementById("standings");
            standingsList.innerHTML = "";

            for (var i = 0; i < currentIndex; i++) {
                var listItem = document.createElement("li");
                listItem.innerText = standings[i];
                standingsList.appendChild(listItem);
            }
        }

        loadTeams();
    </script>

