set( target chapter03 )
set( chapter03_SOURCES
	main.cpp
	scenesubroutine.cpp
	scenediffuse.cpp
	scenetwoside.cpp
	sceneflat.cpp
	scenediscard.cpp
        scenephong.cpp)

add_executable( ${target} ${chapter03_SOURCES} )

target_compile_definitions(${target}
		PRIVATE
		GLFW_INCLUDE_NONE
		)

target_link_libraries( ${target}
		PRIVATE
		ingredients
		glfw
		${OPENGL_gl_LIBRARY}
		)

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/shader DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
