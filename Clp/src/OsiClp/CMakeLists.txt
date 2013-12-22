file(
	GLOB_RECURSE
	OSI_HEADERS
	*.hpp
	*.h
)
file(
	GLOB_RECURSE
	OSI_SRCS
	*.cpp
)
ADD_LIBRARY(lib_OsiClpSolver ${OSI_HEADERS} ${OSI_SRCS})
