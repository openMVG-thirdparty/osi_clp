#==============================================================================                                                                                                                                                                                             

PROJECT(COIN_OR_OSI_CLP C CXX)

# CMake version control
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

################
INCLUDE_DIRECTORIES(.
CoinUtils/src/
Clp/src/
Clp/test/
Osi/src/OsiCommonTest/
Osi/src/Osi/
Clp/src/OsiClp/
)

#Optimisation gcc
IF(CMAKE_COMPILER_IS_GNUCC OR CMAKE_COMPILER_IS_GNUCXX) 
  ADD_DEFINITIONS(-O3 -Wall -D_FILE_OFFSET_BITS=64 -D_LARGEFILE_SOURCE -ffast-math)
ENDIF(CMAKE_COMPILER_IS_GNUCC OR CMAKE_COMPILER_IS_GNUCXX)

IF(MSVC)
  ADD_DEFINITIONS( -D_CRT_SECURE_NO_WARNINGS -D_CRT_SECURE_NO_DEPRECATE -DSAMPLEDIR="..\..\..\..\Data\Sample\\") 
ENDIF(MSVC)

ADD_SUBDIRECTORY(Osi)
ADD_SUBDIRECTORY(Clp)
ADD_SUBDIRECTORY(CoinUtils)
