cmake_minimum_required (VERSION 2.6)

project (fourth_example)

find_package(PkgConfig)

pkg_check_modules(LIBNS3_CORE libns3.26-core-debug)
pkg_check_modules(LIBNS3_NETWORK libns3.26-network-debug)
pkg_check_modules(LIBNS3_CSMA libns3.26-csma-debug)
pkg_check_modules(LIBNS3_INTERNET libns3.26-internet-debug)
pkg_check_modules(LIBNS3_POINT_TO_POINT libns3.26-point-to-point-debug)
pkg_check_modules(LIBNS3_APPLICATIONS libns3.26-applications-debug)
pkg_check_modules(LIBNS3_WIFI libns3.26-wifi-debug)

link_directories(
)
include_directories(
	${LIBNS3_CORE_INCLUDE_DIRS}
)
add_executable(fourth_example fourth_example.cpp)
target_link_libraries(fourth_example
	${LIBNS3_CORE_LIBRARIES}
)