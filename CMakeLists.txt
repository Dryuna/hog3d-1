cmake_minimum_required(VERSION 2.8.3)
project(hog3d)

find_package(catkin REQUIRED COMPONENTS roscpp rospy)
find_package(OpenCV REQUIRED)
find_package(Boost REQUIRED COMPONENTS thread)

catkin_package()

include_directories(include)

 add_library(hog3d
   src/FastVideoGradientComputer.cpp
   src/extractFeatures.cpp
   src/FastHog3DComputer.cpp
   src/ffpp/Codec.cpp
   src/ffpp/CodecContext.cpp
   src/ffpp/FlipContext.cpp
   src/ffpp/FormatContext.cpp
   src/ffpp/Frame.cpp
   src/ffpp/InputFormat.cpp
   src/ffpp/InputFormatContext.cpp
   src/ffpp/OutputFormat.cpp
   src/ffpp/OutputFormatContext.cpp
   src/ffpp/Packet.cpp
   src/ffpp/PixelFormat.c
   src/ffpp/ScalerContext.cpp
   src/ffpp/Stream.cpp
   src/opencv/functions.cpp
   src/opencv/IplImageWrapper.cpp
   src/opencv/Video.cpp
 )

## Declare a cpp executable
# add_executable(hog3d_node src/hog3d_node.cpp)

## Add cmake target dependencies of the executable/library
## as an example, message headers may need to be generated before nodes
# add_dependencies(hog3d_node hog3d_generate_messages_cpp)

## Specify libraries to link a library or executable target against
# target_link_libraries(hog3d_node
#   ${catkin_LIBRARIES}
# )

