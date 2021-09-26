cmake_minimum_required(VERSION 3.2.1)
project(TitanC-Forked CXX)

find_package(CURL CONFIG REQUIRED)
find_package(RapidJSON CONFIG REQUIRED)
find_package(LibXml2 CONFIG REQUIRED)

file(GLOB SOURCES ${CMAKE_CURRENT_LIST_DIR}/TitanRewrite/*.cpp)
file(GLOB HEADERS ${CMAKE_CURRENT_LIST_DIR}/include/*.h)

add_executable(TitanC-Forked ${SOURCES} ${HEADERS})

target_link_libraries(TitanC-Forked PUBLIC CURL::libcurl)
target_link_libraries(TitanC-Forked PUBLIC rapidjson)
target_link_libraries(TitanC-Forked PUBLIC LibXml2::LibXml2)

target_include_directories(TitanC-Forked PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)