SkySports Project using Mysql

show databases;
create database Project_2_SkySports;

use project_2_skysports;
select * from sql_skysports_project16875987300 ;
alter database sql_skysports_project16875987300 rename table Skysports_1;

rename table sql_skysports_project16875987300 to Skysports_1;
rename table sql_skysports_project16875987301 to Skysports_2;

select * from skysports_1 s;
select * from skysports_2 s ;



#1. Import both the .CSV files in Dbeaver under the database name Sky_Sports 
#2. Write an sql query to show all the UNIQUE team names 

select distinct(team) from skysports_1 s ;

#3. Write an SQL query to show name of team which has rank 1 from group 7

select team from skysports_1 where `rank` =1 and Team_group  =7;

#4. Write an sql query to show count of all teams 

select distinct (count(team)) Count_of_All_Teams from skysports_1;

#5. Write an SQL query to show matches_played by each team 

select team, matches_Played from skysports_1 s ;

#6. Write an SQL query to show team, percent of wins with respect  to matches_played by each team and name the resulting column 
#as wins_percent 

select team, wins/matches_Played*100 as Wins_Percent from skysports_1 s;

#7. Write an SQL query to show which team has maximum goals_scored and their count 

select team, max(goals_scored) Maximum_Goal from skysports_1 s group by team ; 

#8. Write an SQL query to show percent of draws with respect to matches_played round of to 2 digits by each team 

select team, round(draws/matches_played*100,2) Percent_of_draws from skysports_1 s;

#9. Write an SQL query to show which team has minimum goals_scored and their count 

select team, min(goals_scored) Minimum_Goal from skysports_1 s group by team ; 

#10. Write an SQL query to show percent of losses with respect to matches_played by each team in ascending order by losses and 
#name the resulting column as losses_percent 

select team, losses/matches_played*100 losses_Percent
from skysports_1 s order by losses asc;

#11. Write an SQL query to show the average goal_difference

select avg(goal_difference) Avg_Goal_Difference from skysports_1;

#12. Write an SQL query to show name of the team where points are 0

select team , points from skysports_1 s where points = 0;

#13. Write a SQL query to show all data where expected_goal_scored  is less than exp_goal_conceded 

select * from skysports_1 s where expected_goal_scored < exp_goal_conceded ;

#14. Write an SQL query to show data where exp_goal_difference is in between -0.5 and 0.5 

select * from skysports_1 s where exp_goal_difference between -0.5 and 0.5;

#15. Write an SQL query to show all data in ascending order by exp_goal_difference_per_90 

select * from skysports_1 s order by exp_goal_difference asc;

#16. Write an SQL query to show team which has maximum number of players_used 

select team, max(players_used) Max_players_used from skysports_2 group by team order by Max_players_used desc ; 

select team, max(players_used) Max_players_used from skysports_2 group by team order by Max_players_used desc ; 

#17. Write an SQL query to show each team name and avg_age in ascending order by avg_age

select team, avg_age from skysports_2 order by avg_age asc;

#18. Write an sql query to show average possession of teams 

select avg(possession) Avg_possession from skysports_2 s ; 

select round(avg(possession),2) Avg_possession from skysports_2 s ; 

#19. Write a SQL query to show team which has played atleast 5 games 

select team, games 
from skysports_2 s 
where games =5;

#20. Write an SQL query to show all data for which minutes is greater than 600

select * from skysports_2 
where minutes >600;

#21. Write an SQL query to show team, goals, assists in ascending order by goals

select team, goals, assists 
from skysports_2 s 
order by goals asc;

#22. Write an SQL query to show team, pens_made, pens_att in descending order by pens_made

select team, pens_made, pens_att 
from skysports_2 s 
order by pens_made desc;

#23. Write an SQL query to show team, cards_yellow, cards_red where cards_red is equal to 1 in ascending order by cards_yellow 

select team, cards_yellow, cards_red 
from skysports_2 s 
where cards_red = 1 
order by cards_yellow asc;

#24. Write an SQL query to show team, goals_per90, assists_per90, goals_assists_per90 in descending order by goals_assists_per90 

select team, goals_per90, assists_per90, goals_assists_per90 
from skysports_2 s 
order by goals_assists_per90 desc;

#25. Write an SQL query to show team, goals_pens_per90, goals_assists_pens_per90 in ascending order by goals_assists_pens_per90

select team, goals_pens_per90, goals_assists_pens_per90 
from skysports_2 s 
order by goals_assists_pens_per90 asc;

#26. Write an SQL query to show team, shots, shots_on_target, shots_on_target_pct where shots_on_target_pct is less than 30 
#in ascending order by shots_on_target_pct 

select team, shots, shots_on_target, shots_on_target_pct 
from skysports_2 s 
where shots_on_target_pct <30 
order by shots_on_target_pct asc;

#27. Write an SQL query to show team, shots_per90, shots_on_target_per90 for team Belgium 

select team, shots_per90, shots_on_target_per90 from skysports_2 s where team = 'belgium';

#28. Write an SQL query to show team, goals_per_shot, goals_per_shot_on_target, average_shot_distance in descending 
#order by average_shot_distance

select team, goals_per_shot, goals_per_shot_on_target, average_shot_distance 
from skysports_2 s 
order by average_shot_distance ;

#29. Write an SQL query to show team, errors, touches for which errors is 0 and touches is less than 1500

select team, errors, touches from skysports_2 s where errors =0 and touches < 1500;

#30. Write an SQL query to show team, fouls which has maximum number of fouls

select team, max(fouls) from skysports_2 s group by team;

#31. Write an SQL query to show team, offisdes which has offsides less than 10 or greater than 20 

select team, offsides from skysports_2 s where offsides <10 or offsides >20;

#32. Write an SQL query to show team, aerials_won, aerials_lost, aerials_won_pct in descending order by aerials_won_pct

select team, aerials_won, aerials_lost, aerials_won_pct from skysports_2 s order by aerials_won_pct desc;

#33. Write an SQL query to show number of teams each group has! 

select count(Team_group) from skysports_1;

#34. Write a SQL query to show team names group 6 has 

select team from skysports_1 s where Team_group  = 6;

#35. Write an SQL query to show Australia belongs to which group 

select team_group, team  from skysports_1 s where team  = 'Australia';

#36. Write an SQL query to show group, average wins by each group 

select * from skysports_1 s ;

select team_group, avg(wins) from skysports_1 s group by team_group;

#37. Write an SQL query to show group, maximum expected_goal_scored by each group in ascending order by expected_goal_scored 

select Team_group  , max(expected_goal_scored) Exp_Goal_Scored from skysports_1 s
group by Team_group order by Exp_Goal_Scored;

#38. Write an SQL query to show group, minimum exp_goal_conceded by each group in descending order by exp_goal_conceded 

select Team_group , min(expected_goal_scored)as Min_exp_goal_conceded from skysports_1 s
group by Team_group order by  Min_exp_goal_conceded;

#39. Write an SQL query to show group, average exp_goal_difference_per_90 for each group in ascending order 
#by exp_goal_difference_per_90 

select Team_group , avg(exp_goal_difference_per_90)as exp_goal_differnce from skysports_1 s
group by Team_group order by exp_goal_differnce ;

#40. Write an SQL query to show which team has equal number of goals_scored and goals_against 

select team from skysports_1 s where goals_scored = goals_against ;

#41. Write an SQL query to show which team has maximum players_used

select team, max(players_used) Maximum_players_used from skysports_2 group by team;

#42. Write an SQL query to show team, players_used, avg_age, games, minutes where minutes lessthan 500 and greater than 200 

select team, players_used, avg_age, games, minutes  from skysports_2 s where minutes<500 and minutes>200;

#43. Write an SQL query to show all data of group_stats in ascending order BY points 

@select groupfrom skysports_2 where group_stats order by points;

#44. Write an SQL query to show ALL UNIQUE team in ascending order by team

select distinct (team) from skysports_1 s order by team asc;

#45. Write an SQL query to show average avg_age of each group and arrange it in descending order by avg_age. 

select * from skysports_2;
select * from skysports_1 s ;

select avg(avg_age) Avg_age, team_group
from skysports_2 A join skysports_1 B
on a.team = b.team 
group by team_group
order by avg_age desc ; 

#46. Write an SQL query to show sum of fouls for each group and arrange it in ascending order by fouls.

select sum(fouls) Sum_Of_Fouls, team_group
from skysports_2 A join skysports_1 B
on a.team = b.team 
group by team_group
order by Sum_Of_Fouls; 


#47. Write an SQL query to show total number of games for each group and arrange it in descending order by games. 

select count(games) count_of_games, team_group
from skysports_2 A join skysports_1 B
on a.team = b.team 
group by team_group
order by count_of_games desc;


#48. Write an SQL query to show total number of players_used for each group and arrange it in ascending order by players_used.

select count(players_used) Players_used, team_group
from skysports_2 A join skysports_1 B
on a.team = b.team 
group by team_group
order by players_used asc;


#49. Write an SQL query to show total number of offsides for each group and arrange it in ascending order by offsides. 

select count(offsides) offsides , team_group
from skysports_2 A join skysports_1 B
on a.team = b.team 
group by team_group
order by offsides asc;

#50. Write an SQL query to show average passes_pct for each group and arrange it in descending order by passes_pct. 

select avg(passes_pct) passes_pct , team_group
from skysports_2 A join skysports_1 B
on a.team = b.team 
group by team_group
order by passes_pct desc;

#51. Write an SQL query to show average goals_per90 for each group and arrange it in ascending order by goals_per90. 

select avg(passes_pct) passes_pct , team_group
from skysports_2 A join skysports_1 B
on a.team = b.team 
group by team_group
order by passes_pct asc;

