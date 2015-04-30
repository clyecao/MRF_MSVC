# CMake powered build system for CMVS
# Create by Pierre Moulon
# First draft the 4 june 2010
# Second draft 24 sept 2010
# Third draft (linux) 12 oct 2010 

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(mrf_project CXX)

INCLUDE_DIRECTORIES(
./MRF
./imageLib
./mrfstereo
IF(WIN64_PTHREAD)
	./thirdParty/x64/VC10.0/include
ELSE(WIN64_PTHREAD)
	./thirdParty/x86/VC10.0/include
ENDIF(WIN64_PTHREAD)
)

#if you build on win64 you have to set to true the following variable
SET(WIN64_PTHREAD true)
#SET(WIN64_PTHREAD false)

IF(WIN64_PTHREAD)
  SET(LIB_PNG ${CMAKE_SOURCE_DIR}/thirdParty/x64/VC10.0/lib/libpng13.lib)
  SET(LIB_Z ${CMAKE_SOURCE_DIR}/thirdParty/x64/VC10.0/lib/zlib1.lib)
ELSE(WIN64_PTHREAD)
  SET(LIB_PNG ${CMAKE_SOURCE_DIR}/thirdParty/x86/VC10.0/lib/libpng13.lib)
  SET(LIB_Z ${CMAKE_SOURCE_DIR}/thirdParty/x86/VC10.0/lib/zlib1.lib)
ENDIF(WIN64_PTHREAD)

SET(PRECOMPILED_LIBS ${PTHREAD_LIB})

ADD_SUBDIRECTORY(MRF)
ADD_SUBDIRECTORY(imageLib)
ADD_SUBDIRECTORY(mrfstereo)

