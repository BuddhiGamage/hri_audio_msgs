cmake_minimum_required(VERSION 3.8)
project(hri_audio_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)


find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "action/SpeechToText.action"
  "action/TextToSpeech.action"
  DEPENDENCIES builtin_interfaces std_msgs
)

ament_package()
