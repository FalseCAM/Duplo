cmake_minimum_required(VERSION 2.6.0)

project(duplo)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3 -Wall")

file(GLOB ${CMAKE_PROJECT_NAME}Sources "*.cpp")
file(GLOB ${CMAKE_PROJECT_NAME}Headers "*.h")

add_executable(${CMAKE_PROJECT_NAME} ${${CMAKE_PROJECT_NAME}Sources} ${${CMAKE_PROJECT_NAME}Headers})

if (UNIX)
  install(TARGETS ${CMAKE_PROJECT_NAME}
          RUNTIME DESTINATION bin)
elseif (WIN32)
  install(TARGETS ${CMAKE_PROJECT_NAME}
          DESTINATION .)
endif()
