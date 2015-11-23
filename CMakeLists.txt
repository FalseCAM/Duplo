cmake_minimum_required(VERSION 2.6.0)

project(duplo)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3 -Wall")

file(GLOB ${PROJECT_NAME}Sources "*.cpp")
file(GLOB ${PROJECT_NAME}Headers "*.h")

add_executable(${PROJECT_NAME} ${${PROJECT_NAME}Sources} ${${PROJECT_NAME}Headers})

if (UNIX)
  install(TARGETS ${PROJECT_NAME}
          RUNTIME DESTINATION bin)
elseif (WIN32)
  install(TARGETS ${PROJECT_NAME}
          DESTINATION .)
endif()
