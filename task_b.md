## TAsk2 
task 2 is to do waypoint navigation for the bot. 

I have used slam_toolbox for mapping the map

__ros2 launch slam_toolbox online_async_launch.py__

while moving the bot using teleop_twist_keyboard

__ros2 run teleop_twist_keyboard teleop_twist_keyboard__

and used nav2_map_saver to save the map 

__ros2 run nav2_map_server map_saver_cli -f ~/map__

after saving use nav2bringup to use the saved map

__ros2 launch nav2_bringup bringup_launch.py use_sim_time:=True autostart:=True map:=/home/map.yaml__

open rviz2 with specific format

__ros2 run rviz2 rviz2 -d $(ros2 pkg prefix nav2_bringup)/share/nav2_bringup/rviz/nav2_default_view.rviz__

now set goal and navigate it through the points you want it to go.
