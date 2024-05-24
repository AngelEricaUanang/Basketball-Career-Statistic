<?php
function basketball_player_statistics($player_name, $games_data) {
  
  $total_points = 0;
  $total_rebounds = 0;
  $total_assists = 0;
  $total_steals = 0;
  $total_blocks = 0;
  $total_turnovers = 0;
  $total_fouls = 0;
  $total_minutes_played = 0;

 
  foreach ($games_data as $game) {
    $total_points += $game['points'];
    $total_rebounds += $game['rebounds'];
    $total_assists += $game['assists'];
    $total_steals += $game['steals'];
    $total_blocks += $game['blocks'];
    $total_turnovers += $game['turnovers'];
    $total_fouls += $game['fouls'];
    $total_minutes_played += $game['minutes_played'];
  }

  
  $average_points = $total_points / count($games_data);
  $average_rebounds = $total_rebounds / count($games_data);
  $average_assists = $total_assists / count($games_data);
  $average_steals = $total_steals / count($games_data);
  $average_blocks = $total_blocks / count($games_data);
  $average_turnovers = $total_turnovers / count($games_data);
  $average_fouls = $total_fouls / count($games_data);
  $average_minutes_played = $total_minutes_played / count($games_data);

 
  echo "<h2>$player_name Basketball Career Statistics</h2>";
  echo "<table>";
  echo "<tr><th>Statistic</th><th>Total</th><th>Average</th></tr>";
  echo "<tr><td>Points</td><td>$total_points</td><td>$average_points</td></tr>";
  echo "<tr><td>Rebounds</td><td>$total_rebounds</td><td>$average_rebounds</td></tr>";
  echo "<tr><td>Assists</td><td>$total_assists</td><td>$average_assists</td></tr>";
  echo "<tr><td>Steals</td><td>$total_steals</td><td>$average_steals</td></tr>";
  echo "<tr><td>Blocks</td><td>$total_blocks</td><td>$average_blocks</td></tr>";
  echo "<tr><td>Turnovers</td><td>$total_turnovers</td><td>$average_turnovers</td></tr>";
  echo "<tr><td>Fouls</td><td>$total_fouls</td><td>$average_fouls</td></tr>";
  echo "<tr><td>Minutes Played</td><td>$total_minutes_played</td><td>$average_minutes_played</td></tr>";
  echo "</table>";
}


$games_data = array(
  array('points' => 20, 'rebounds' => 10, 'assists' => 5, 'steals' => 3, 'blocks' => 2, 'turnovers' => 2, 'fouls' => 3, 'minutes_played' => 30),
  array('points' => 15, 'rebounds' => 8, 'assists' => 4, 'steals' => 2, 'blocks' => 1, 'turnovers' => 3, 'fouls' => 4, 'minutes_played' => 28),
);


$player_name = "Angel Erica Uanang";

basketball_player_statistics($player_name, $games_data);
?>


