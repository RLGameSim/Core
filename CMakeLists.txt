cmake_minimum_required(VERSION 3.8)

project(RLGameSim_Core LANGUAGES CXX)

add_subdirectory(RocketSim)

add_executable(${PROJECT_NAME})

target_include_directories(${PROJECT_NAME} PRIVATE RocketSim/src RocketSim/libsrc)

if (UNIX)
    target_link_libraries(${PROJECT_NAME} RocketSim pthread)
else (UNIX)
    target_link_libraries(${PROJECT_NAME} RocketSim)
endif (UNIX)

target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_20)
