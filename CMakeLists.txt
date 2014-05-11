cmake_minimum_required(VERSION 2.8.3)
project(hog3d)

find_package(catkin REQUIRED COMPONENTS roscpp rospy)
find_package(OpenCV REQUIRED)
find_package(Boost REQUIRED COMPONENTS thread program_options)

catkin_package()

include_directories(include)

add_library(${PROJECT_NAME}
   src/FastVideoGradientComputer.cpp
   src/extractFeatures.cpp
   src/FastHog3DComputer.cpp
   src/opencv/functions.cpp
   src/opencv/IplImageWrapper.cpp
   src/opencv/Video.cpp
)

add_executable(extract_features src/extractFeatures.cpp)
target_link_libraries(extract_features
  ${PROJECT_NAME}
  ${catkin_LIBRARIES}
  ${Boost_LIBRARIES})

