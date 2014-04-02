cmake_minimum_required(VERSION 2.8.3)
project(teo_remote)

find_package(catkin REQUIRED 
roscpp std_msgs geometry_msgs message_generation teo_msgs tf )
catkin_package(
)

###########
## Build ##
###########

## Declare a cpp executable
add_executable(teo_odometry src/teo_odometry.cpp)

## Specify libraries to link a library or executable target against
target_link_libraries(teo_odometry ${catkin_LIBRARIES})

#add_dependencies(remap_odometry teo_remote_generate_messages_cpp)
add_dependencies(teo_odometry teo_remote_gencpp teo_remote_generate_messages_cpp)

