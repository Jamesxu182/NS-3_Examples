cmake_minimum_required (VERSION 2.6)

project (sixth_example)

find_package(PkgConfig)

pkg_check_modules(LIBNS3_CORE libns3.26-core-debug)
pkg_check_modules(LIBNS3_NETWORK libns3.26-network-debug)
pkg_check_modules(LIBNS3_INTERNET libns3.26-internet-debug)
pkg_check_modules(LIBNS3_POINT_TO_POINT libns3.26-point-to-point-debug)
pkg_check_modules(LIBNS3_APPLICATIONS libns3.26-applications-debug)

link_directories(
	${LIBNS3_CORE_LIBRARY_DIRS}
	${LIBNS3_NETWORK_LIBRARY_DIRS}
	${LIBNS3_INTERNET_LIBRARY_DIRS}
	${LIBNS3_POINT_TO_POINT_LIBRARY_DIRS}
	${LIBNS3_APPLICATIONS_LIBRARY_DIRS}
)
include_directories(
	${LIBNS3_CORE_INCLUDE_DIRS}
	${LIBNS3_NETWORK_INCLUDE_DIRS}
	${LIBNS3_INTERNET_INCLUDE_DIRS}
	${LIBNS3_POINT_TO_POINT_INCLUDE_DIRS}
	${LIBNS3_APPLICATIONS_INCLUDE_DIRS}
)
add_executable(sixth_example sixth_example.cpp)
target_link_libraries(sixth_example
	${LIBNS3_CORE_LIBRARIES}
	${LIBNS3_NETWORK_LIBRARIES}
	${LIBNS3_INTERNET_LIBRARIES}
	${LIBNS3_POINT_TO_POINT_LIBRARIES}
	${LIBNS3_APPLICATIONS_LIBRARIES}
)