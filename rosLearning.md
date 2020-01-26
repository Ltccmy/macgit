### Ros learning

-----

#### nodes

```
$ roscore #run first; Only one roscore needs to be running.
$ rosnode list #display info about the nodes that are currently running
$ rosnode info /rosout  #display more info about the specific node
# in this case it publishes  * /rosout_agg [rosgraph_msgs/Log]
$ rosrun [package_name] [node_name] #run the node from a package 
$ rosrun turtlesim turtlesim_node #an example 
#tip: always remember to new terminal
$ rosrun turtlesim turtlesim_node __name:=my_turtle #tiny change to modify the name of the node  #attention before name two _ && :=
$ rosnode ping my_turtle # it can be used to detect whether the node is alive

$ rosrun rqt_graph rqt_graph  #it can be used to display what's happening between the nodes remember to open a new terminal
$ rostopic -h  #get info on how to use rostopic when using specify the topic
$ rostopic echo /turtle1/cmd_vel # this means another node subscribe from the topic /turtle1/cmd_vel

$ rostopic list -h # get info on how to use rostopic list
-v, --verbose         list full details about each topic
$ rostopic list -v  # this enables us to known fully about the topics
$ rostopic type /turtle1/cmd_vel # info on the type of the topic 
$ rosmsg show geometry_msgs/Twist # give further info on the type
#if we want to combine them together 
#$ rostopic type /turtle1/cmd_vel | rosmsg show
$ rostopic pub -1 /turtle1/cmd_vel geometry_msgs/Twist -- '[2.0, 0.0, 0.0]' '[0.0, 0.0, 1.8]' # this is what we do when we need to control the node by publish info designed by ourselves && with words
# -1: rostopic to send  only one msg then exit
#/turtle1/cmd_vel  name
#geometry_msgs/Twist type
# -- none of the following is a option for negetive numbers
# '[2.0, 0.0, 0.0]' '[0.0, 0.0, 1.8]'  actully YAML list
$ rostopic pub /turtle1/cmd_vel geometry_msgs/Twist -r 1 -- '[2.0, 0.0, 0.0]' '[0.0, 0.0, -1.8]' # an example if we want give a steady stream of commands -r 1 means 1 HZ
$ rostopic hz /turtle1/pose# learn the rate the pose reported
$ rosrun rqt_plot rqt_plot# this shows how the parameters change 

$ rosparam dump params.yaml#will dump this to the current space

```

