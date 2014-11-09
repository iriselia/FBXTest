cmake_minimum_required( VERSION 2.8 )

find_package(OpenGL REQUIRED)

#ADD_DEFINITIONS("-D_GLFW_USE_OPENGL" "-D_GLFW_WIN32" "-D_GLFW_WGL")
#add_definitions("-D_GLFW_USE_CONFIG_H")


SET( INCLUDE_DIRS
	${fbxsdk_INCLUDE_DIRS}
	${common_INCLUDE_DIRS}
)
SET( LINK_DIRS
)
SET( LINK_LIBS
	Common
#	${CMAKE_SOURCE_DIR}/lib/x86/debug/libfbxsdk.lib
	${CMAKE_SOURCE_DIR}/lib/x86/debug/libfbxsdk-md.lib
)

parse_directory_name(PROJECT_NAME)
project( ${PROJECT_NAME} )
create_project_ex(CONSOLE "${INCLUDE_DIRS}" "${LINK_DIRS}" "${LINK_LIBS}")
