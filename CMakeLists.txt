cmake_minimum_required(VERSION 2.8.9)
project(spine)

if(MSVC)
	message("MSCV detected")
	set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS}")
	set (CMAKE_C_FLAGS "${CMAKE_CXX_FLAGS}")
else()
	set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wunused-value -Wno-c++11-long-long -Wno-variadic-macros -Werror -Wextra -pedantic -Wnonportable-include-path -Wshadow -std=c89")
	set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wunused-value -Wno-c++11-long-long -Wno-variadic-macros -Werror -Wextra -Wnon-virtual-dtor -pedantic -Wnonportable-include-path -Wshadow -std=c++03 -fno-exceptions -fno-rtti")
endif()

set(CMAKE_VERBOSE_MAKEFILE ON)
set(SPINE_SFML FALSE CACHE BOOL FALSE)
set(SPINE_COCOS2D_OBJC FALSE CACHE BOOL FALSE)
set(SPINE_COCOS2D_X FALSE CACHE BOOL FALSE)

#add_subdirectory(spine-c)
add_subdirectory(spine-cpp)