if (NOT "${HOST_CMAKE_CXX_COMPILER}" STREQUAL "")
    set (CMAKE_CXX_COMPILER "${HOST_CMAKE_CXX_COMPILER}")
endif()

set(CMAKE_C_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS "-std=c++11 -Wall")
set(CMAKE_CXX_LINK_FLAGS "-std=c++11 -Wall")

set(SOURCES
    ApiGen.cpp
    EntryPoint.cpp
    main.cpp
    Parser.cpp
    strUtils.cpp
    TypeFactory.cpp)

add_executable(emugen ${SOURCES})
set_target_properties(emugen PROPERTIES COMPILE_FLAGS "-m64" LINK_FLAGS "-m64")
