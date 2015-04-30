FILE(GLOB H_FILES ./*.h)
SET(CPP_FILES mrf.cpp ICM.cpp GCoptimization.cpp graph.cpp maxflow.cpp
       MaxProdBP.cpp LinkedBlockList.cpp regions-maxprod.cpp
       TRW-S.cpp BP-S.cpp)
SET(LIBRARY_OUTPUT_PATH "../bin")
ADD_LIBRARY(libMRF STATIC ${H_FILES} ${CPP_FILES})

SET(EXECUTABLE_OUTPUT_PATH "../bin")
ADD_EXECUTABLE(example example.cpp)
TARGET_LINK_LIBRARIES(example libMRF) # libMRF