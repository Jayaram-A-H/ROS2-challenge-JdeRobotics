## TAsk2 
task 2 is to do waypoint navigation for the bot. 

I have used slam_toolbox for mapping the map

ros2 launch slam_toolbox online_async_launch.py

while moving the bot using teleop_twist_keyboard

ros2 run teleop_twist_keyboard teleop_twist_keyboard

and used nav2_map_saver to save the map 

ros2 run nav2_map_server map_saver_cli -f ~/map

after saving use nav2bringup to use the saved map

ros2 launch nav2_bringup bringup_launch.py use_sim_time:=True autostart:=True map:=/home/map.yaml

open rviz2 with specific format

ros2 run rviz2 rviz2 -d $(ros2 pkg prefix nav2_bringup)/share/nav2_bringup/rviz/nav2_default_view.rviz

now set goal and navigate it through the points you want it to go.
