Assignment of the Intelligent Robotics 2022-2023 course at University of Padua, Italy.

Group 24\
Edoardo Bastianello\
Stefano Binotto\
Gionata Grotto
<br/><br/>

PROJECT DESCRIPTION:
Program a robot that has to:
- navigate to a table with 3 objects of different colors
- detect the required object by scanning the tag
- pick the required object
- bring the object to one of the 3 target tables, depending on the color of the required object
- repeat the previous steps for each of the 3 objects
<br/><br/>

COMMANDS TO RUN THE PROGRAM:
roslaunch tiago_iaslab_simulation start_simulation.launch world_name:=ias_lab_room_full_tables\
roslaunch tiago_iaslab_simulation apriltag.launch\
roslaunch tiago_iaslab_simulation navigation.launch\
rosrun tiago_iaslab_simulation human_node\
rosrun tiago_iaslab_simulation robot_srv\
rosrun tiago_iaslab_simulation detection_server\
rosrun tiago_iaslab_simulation pick_server\
rosrun tiago_iaslab_simulation place_server\
rosrun tiago_iaslab_simulation client_human_navigate
<br/><br/>

FILES IN THIS PROJECTS
CPP FILES
client_human_navigate.cpp 
detection_server.cpp (used to detect the objects on the table)
Human_node.cpp 
Human.cpp
pick_server.cpp (used to for the pick routine in front of the table)
place_server.cpp (used for the place routine in front of the cylindrical tables)
robot_srv.cpp (used for the navigation)
utils.cpp (contains all the external functions used in other files)
<br/><br/>

HEADER FILES
Human.h
utils.h (header file for utils.cpp file)
variables.h (this file is inside the include directory and contains the values we set for the parameters/dimensions of objects/coordinates we used in the code)
<br/><br/>

ACTION MESSAGE: 
Move.action (used for communication between client_human_navigate.cpp and robot_srv.cpp)


SERVICE FILES:
srv_detect.srv (used for communication between client_human_navigate.cpp and detection_server.cpp)
pickObj.srv (used for communication between client_human_navigate.cpp and pick_server.cpp)
placeObj.srv (used for communication between client_human_navigate.cpp and place_server.cpp)
Objs.srv (used for communication between client_human_navigate.cpp and Human_node.cpp)



