file(GLOB_RECURSE sources src/*.c)

idf_component_register(
	SRCS
		${sources}
	INCLUDE_DIRS
		"include"
)

target_compile_options(
	${COMPONENT_LIB}
	PRIVATE
	-Wno-char-subscripts
	-Wno-implicit-fallthrough
)

target_compile_definitions(
	${COMPONENT_LIB}
	PRIVATE
	NDEBUG
	__ANDROID__
)
