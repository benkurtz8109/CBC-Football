<!DOCTYPE html>
<html>
<head>
  <title>CBC Football Schedule & Standings</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f6f9;
      margin: 0;
      padding: 20px;
    }

    h1 {
      text-align: center;
    }

    .container {
      max-width: 1000px;
      margin: auto;
    }

    .week-column {
      border-right: 2px solid #e5e7eb; 
    }
  
    table {
      width: 100%;
      border-collapse: collapse;
      margin-bottom: 40px;
      background: white;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }

    .winner {
      background-color: #dcfce7; /* light green */
      font-weight: bold;
    }
  
    th, td {
      padding: 10px;
      text-align: center;
      border-bottom: 1px solid #ddd;
    }

    th {
      background-color: #b91c1c;
      color: white;
    }

    tr:hover {
      background-color: #f1f1f1;
    }

    .section-title {
      margin-top: 40px;
      font-size: 24px;
      font-weight: bold;
    }
  
  .disclaimer {
  margin-top: 40px;
  padding: 15px 0;
  font-size: 12px;
  color: #777;
  text-align: center;
  border-top: 1px solid #eee;
}
  </style>
</head>
<body>

<div class="container">
  <h1>Central Buckeye Conference Football</h1>

  <div class="section-title">Schedule</div>
  <table id="scheduleTable">
    <thead>
      <tr>
        <th class="week-column">Week</th>
        <th>Home Team</th>
        <th>Home Score</th>
        <th>Away Team</th>
        <th>Away Score</th>
      </tr>
    </thead>
    <tbody></tbody>
  </table>

  <div style="text-align:center; margin-bottom:40px;">

  <button id="prevWeekBtn" style="
    padding: 8px 16px;
    background-color: #b91c1c;
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    margin-right: 10px;
  ">
    Previous
  </button>

  <select id="weekSelect" style="
    padding: 8px;
    font-size: 16px;
    border-radius: 5px;
  ">
  </select>

  <button id="nextWeekBtn" style="
    padding: 8px 16px;
    background-color: #b91c1c;
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    margin-left: 10px;
  ">
    Next
  </button>

</div>  
  <div class="section-title">Kenton Trail Standings</div>
  <table id="standingsTable">
    <thead>
  <tr>
    <th>Team</th>
    <th>Conf Wins</th>
    <th>Conf Losses</th>
    <th>Conf Win %</th>
    <th>Overall Wins</th>
    <th>Overall Losses</th>
    <th>Overall Win %</th>
  </tr>
</thead>
    <tbody></tbody>
  </table>
  
  <div class="section-title">Mad River Standings</div>
  <table id="madRiverTable">
    <thead>
  <tr>
    <th>Team</th>
    <th>Conf Wins</th>
    <th>Conf Losses</th>
    <th>Conf Win %</th>
    <th>Overall Wins</th>
    <th>Overall Losses</th>
    <th>Overall Win %</th>
  </tr>
</thead>
    <tbody></tbody>
  </table>
  
<footer class="disclaimer">
  <p>
    This website is an independent project and is not affiliated with, endorsed by, or officially connected to the Central Buckeye Conference (CBC).
  </p>
</footer>  
  
</div>

<script>
  const kentonTrail = [
  "London",
  "Jonathan Alder",
  "Bellefontaine",
  "Urbana",
  "Kenton Ridge",
  "Tecumseh"
];

const madRiver = [
  "Benjamin Logan",
  "Graham",
  "Northwestern",
  "Shawnee",
  "Indian Lake",
  "North Union"
];
  
  const schedule = [
  // Kenton Trail
  { week: 6, home: "Urbana", away: "London", homeScore: 0, awayScore: 47 },
  { week: 6, home: "Tecumseh", away: "Jonathan Alder", homeScore: 7, awayScore: 31 },
  { week: 6, home: "Bellefontaine", away: "Kenton Ridge", homeScore: 23, awayScore: 21 },
  { week: 7, home: "Bellefontaine", away: "London", homeScore: 0, awayScore: 48 },
  { week: 7, home: "Jonathan Alder", away: "Urbana", homeScore: 28, awayScore: 21 },
  { week: 7, home: "Kenton Ridge", away: "Tecumseh", homeScore: 49, awayScore: 20 },
  { week: 8, home: "London", away: "Jonathan Alder", homeScore: 38, awayScore: 0 },
  { week: 8, home: "Tecumseh", away: "Bellefontaine", homeScore: 28, awayScore: 34 },
  { week: 8, home: "Urbana", away: "Kenton Ridge", homeScore: 28, awayScore: 21 },
  { week: 9, home: "Tecumseh", away: "London", homeScore: 0, awayScore: 37 },
  { week: 9, home: "Kenton Ridge", away: "Jonathan Alder", homeScore: 33, awayScore: 35 },
  { week: 9, home: "Bellefontaine", away: "Urbana", homeScore: 23, awayScore: 16 },
  { week: 10, home: "London", away: "Kenton Ridge", homeScore: 30, awayScore: 0 },
  { week: 10, home: "Jonathan Alder", away: "Bellefontaine", homeScore: 42, awayScore: 7 },
  { week: 10, home: "Urbana", away: "Tecumseh", homeScore: 30, awayScore: 28 },

  // Mad River
  { week: 6, home: "North Union", away: "Indian Lake", homeScore: 14, awayScore: 17 },
  { week: 6, home: "Graham", away: "Benjamin Logan", homeScore: 26, awayScore: 21 },
  { week: 6, home: "Shawnee", away: "Northwestern", homeScore: 13, awayScore: 28 },
  { week: 7, home: "Indian Lake", away: "Shawnee", homeScore: 45, awayScore: 0 },
  { week: 7, home: "Graham", away: "Northwestern", homeScore: 48, awayScore: 21 },
  { week: 7, home: "Benjamin Logan", away: "North Union", homeScore: 13, awayScore: 14 },
  { week: 8, home: "Benjamin Logan", away: "Indian Lake", homeScore: 14, awayScore: 17 },
  { week: 8, home: "Shawnee", away: "Graham", homeScore: 7, awayScore: 42 },
  { week: 8, home: "Northwestern", away: "North Union", homeScore: 20, awayScore: 28 },
  { week: 9, home: "Graham", away: "Indian Lake", homeScore: 21, awayScore: 24 },
  { week: 9, home: "North Union", away: "Shawnee", homeScore: 48, awayScore: 14 },
  { week: 9, home: "Northwestern", away: "Benjamin Logan", homeScore: 0, awayScore: 48 },
  { week: 10, home: "Indian Lake", away: "Northwestern", homeScore: 49, awayScore: 6 },
  { week: 10, home: "North Union", away: "Graham", homeScore: 35, awayScore: 39 },
  { week: 10, home: "Benjamin Logan", away: "Shawnee", homeScore: 40, awayScore: 13 }, 
  
  // Both Divisions
  { week: 1, home: "Kenton Ridge", away: "Graham", homeScore: 27, awayScore: 28 },
  { week: 3, home: "Urbana", away: "Benjamin Logan", homeScore: 24, awayScore: 41 },
  { week: 3, home: "Tecumseh", away: "Shawnee", homeScore: 14, awayScore: 12 },
  { week: 4, home: "Indian Lake", away: "London", homeScore: 14, awayScore: 44 },
  { week: 4, home: "North Union", away: "Jonathan Alder", homeScore: 23, awayScore: 42 },
  { week: 4, home: "Benjamin Logan", away: "Bellefontaine", homeScore: 10, awayScore: 28 },
  { week: 4, home: "Shawnee", away: "Kenton Ridge", homeScore: 14, awayScore: 42 },
  { week: 4, home: "Northwestern", away: "Tecumseh", homeScore: 42, awayScore: 20 },
  { week: 4, home: "Graham", away: "Urbana", homeScore: 67, awayScore: 47 },
  { week: 5, home: "Jonathan Alder", away: "Shawnee", homeScore: 55, awayScore: 20 },
  { week: 5, home: "Bellefontaine", away: "Indian Lake", homeScore: 21, awayScore: 45 },
  { week: 5, home: "Urbana", away: "North Union", homeScore: 27, awayScore: 46 },
  { week: 5, home: "Kenton Ridge", away: "Northwestern", homeScore: 21, awayScore: 17 },
  { week: 5, home: "Tecumseh", away: "Benjamin Logan", homeScore: 12, awayScore: 37 },
  { week: 5, home: "London", away: "Graham", homeScore: 42, awayScore: 0 },
  
  //Non-conference
  { week: 1, home: "New Albany", away: "London", homeScore: 11, awayScore: 14 },
  { week: 1, home: "Bellefontaine", away: "Sidney", homeScore: 55, awayScore: 21 },
  { week: 1, home: "Northeastern", away: "Urbana", homeScore: 35, awayScore: 28 },
  { week: 1, home: "Fairborn", away: "Tecumseh", homeScore: 41, awayScore: 6 },
  { week: 1, home: "West Liberty-Salem", away: "Jonathan Alder", homeScore: 7, awayScore: 33 },
  { week: 1, home: "Pleasant", away: "North Union", homeScore: 16, awayScore: 13 },
  { week: 1, home: "Bath", away: "Indian Lake", homeScore: 50, awayScore: 21 },
  { week: 1, home: "Bluffton", away: "Benjamin Logan", homeScore: 33, awayScore: 30 },
  { week: 1, home: "Southeastern Local", away: "Northwestern", homeScore: 7, awayScore: 50 },
  { week: 1, home: "Shawnee", away: "Greenon", homeScore: 14, awayScore: 34 },
  { week: 2, home: "Jonathan Alder", away: "Columbus Academy" , homeScore: 14, awayScore: 12 },
  { week: 2, home: "Bellbrook", away: "Bellefontaine", homeScore: 34, awayScore: 0 },
  { week: 2, home: "Urbana", away: "Mechanicsburg", homeScore: 47, awayScore: 43 },
  { week: 2, home: "London", away: "Chillicothe", homeScore: 53, awayScore: 14 },
  { week: 2, home: "Carroll", away: "Tecumseh", homeScore: 16, awayScore: 30 },
  { week: 2, home: "Kenton Ridge", away: "Northridge", homeScore: 34, awayScore: 0 },
  { week: 2, home: "Milton-Union", away: "Graham", homeScore: 7, awayScore: 35 },
  { week: 2, home: "North Union", away: "Liberty Union", homeScore: 44, awayScore: 14 },
  { week: 2, home: "Indian Lake", away: "Fairbanks", homeScore: 31, awayScore: 8 },
  { week: 2, home: "Benjamin Logan", away: "West Liberty-Salem", homeScore: 24, awayScore: 0 },
  { week: 2, home: "Northwestern", away: "Greenon", homeScore: 42, awayScore: 7 },
  { week: 2, home: "Shawnee", away: "Brookville", homeScore: 7, awayScore: 49 },
  { week: 3, home: "Jonathan Alder", away: "Bloom Carroll", homeScore: 14, awayScore: 10 },
  { week: 3, home: "Westerville Central", away: "Bellefontaine", homeScore: 23, awayScore: 6 },
  { week: 3, home: "Batavia", away: "Kenton Ridge", homeScore: 35, awayScore: 42 },
  { week: 3, home: "London", away: "Franklin Heights", homeScore: 56, awayScore: 14 },
  { week: 3, home: "Graham", away: "Covington", homeScore: 49, awayScore: 8 },
  { week: 3, home: "North Union", away: "Northmor", homeScore: 19, awayScore: 13 },
  { week: 3, home: "Miami East", away: "Northwestern", homeScore: 45, awayScore: 21 },
  { week: 3, home: "Indian Lake", away: "Allen East", homeScore: 50, awayScore: 20 }
  
  ];
  
  let currentWeek = 1;

const weeks = [...new Set(schedule.map(game => game.week))].sort((a,b)=>a-b);
  
  const kentonGames = schedule.filter(game =>
  kentonTrail.includes(game.home) && kentonTrail.includes(game.away)
);

const madRiverGames = schedule.filter(game =>
  madRiver.includes(game.home) && madRiver.includes(game.away)
);
  
  function populateWeekDropdown() {
  const select = document.getElementById("weekSelect");
  select.innerHTML = "";

  weeks.forEach(week => {
    const option = document.createElement("option");
    option.value = week;
    option.textContent = "Week " + week;
    select.appendChild(option);
  });

  select.value = currentWeek;
}
  
  function renderSchedule() {
  const tbody = document.querySelector("#scheduleTable tbody");
  tbody.innerHTML = "";

  const weekGames = schedule.filter(game => game.week === currentWeek);

  weekGames.forEach(game => {

    let homeClass = "";
    let awayClass = "";

    if (game.homeScore > game.awayScore) {
      homeClass = "winner";
    } 
    else if (game.awayScore > game.homeScore) {
      awayClass = "winner";
    }

    const row = `
      <tr>
        <td>${game.week}</td>
        <td>${game.home}</td>
        <td class="${homeClass}">${game.homeScore}</td>
        <td>${game.away}</td>
        <td class="${awayClass}">${game.awayScore}</td>
      </tr>
    `;

    tbody.innerHTML += row;
  });
}
    
function calculateStandings(teamList, divisionGames) {
  const standings = {};

  teamList.forEach(team => {
    standings[team] = {
      confWins: 0,
      confLosses: 0,
      overallWins: 0,
      overallLosses: 0
    };
  });

  // Overall record (from full schedule)
schedule.forEach(game => {

  if (game.homeScore > game.awayScore) {

    if (standings[game.home]) {
      standings[game.home].overallWins++;
    }

    if (standings[game.away]) {
      standings[game.away].overallLosses++;
    }

  } else if (game.awayScore > game.homeScore) {

    if (standings[game.away]) {
      standings[game.away].overallWins++;
    }

    if (standings[game.home]) {
      standings[game.home].overallLosses++;
    }

  }
});
  
// Conference record (only games where BOTH teams are in this division)
divisionGames.forEach(game => {

  const homeInDivision = standings[game.home] !== undefined;
  const awayInDivision = standings[game.away] !== undefined;

  // Only count if BOTH teams belong to this division
  if (!homeInDivision || !awayInDivision) return;

  if (game.homeScore > game.awayScore) {
    standings[game.home].confWins++;
    standings[game.away].confLosses++;
  } else if (game.awayScore > game.homeScore) {
    standings[game.away].confWins++;
    standings[game.home].confLosses++;
  }

});
  
  return standings;
}
  
function renderDivisionStandings(teamList, divisionGames, tableId) {
  const standings = calculateStandings(teamList, divisionGames);
  const tbody = document.querySelector(`#${tableId} tbody`);
  tbody.innerHTML = "";

  const sortedTeams = Object.keys(standings).sort((a, b) => {
    const confA = standings[a].confWins / 
      (standings[a].confWins + standings[a].confLosses || 1);
    const confB = standings[b].confWins / 
      (standings[b].confWins + standings[b].confLosses || 1);

    return confB - confA;
  });

  sortedTeams.forEach(team => {
    const s = standings[team];

    const confGames = s.confWins + s.confLosses;
    const overallGames = s.overallWins + s.overallLosses;

    const confPct = confGames === 0 ? "0.000" : 
      (s.confWins / confGames).toFixed(3);

    const overallPct = overallGames === 0 ? "0.000" : 
      (s.overallWins / overallGames).toFixed(3);

    const row = `
      <tr>
        <td>${team}</td>
        <td>${s.confWins}</td>
        <td>${s.confLosses}</td>
        <td>${confPct}</td>
        <td>${s.overallWins}</td>
        <td>${s.overallLosses}</td>
        <td>${overallPct}</td>
      </tr>
    `;

    tbody.innerHTML += row;
  });
}
  
document.getElementById("prevWeekBtn").addEventListener("click", () => {
  const index = weeks.indexOf(currentWeek);
  if (index > 0) {
    currentWeek = weeks[index - 1];
    document.getElementById("weekSelect").value = currentWeek;
    renderSchedule();
  }
});

document.getElementById("nextWeekBtn").addEventListener("click", () => {
  const index = weeks.indexOf(currentWeek);
  if (index < weeks.length - 1) {
    currentWeek = weeks[index + 1];
    document.getElementById("weekSelect").value = currentWeek;
    renderSchedule();
  }
});

document.getElementById("weekSelect").addEventListener("change", (e) => {
  currentWeek = parseInt(e.target.value);
  renderSchedule();
}); 
populateWeekDropdown();
renderSchedule();
renderDivisionStandings(kentonTrail, schedule, "standingsTable");
renderDivisionStandings(madRiver, schedule, "madRiverTable");
  </script>
</body>
</html>