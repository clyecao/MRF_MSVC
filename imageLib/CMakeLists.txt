SET(LIBRARY_OUTPUT_PATH "../bin")

FILE(GLOB H_FILES ./*.h)
SET(CPP_FILES Convert.cpp Convolve.cpp Image.cpp ImageIO.cpp ImageIOpng.cpp RefCntMem.cpp)

ADD_LIBRARY(libImg STATIC ${H_FILES} ${CPP_FILES})