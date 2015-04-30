SET(EXECUTABLE_OUTPUT_PATH "../bin")

FILE(GLOB H_FILES ./*.h)
SET(CPP_FILES mrfstereo.cpp XGetopt.cpp)

ADD_EXECUTABLE(mrfstereo ${H_FILES} ${CPP_FILES})
TARGET_LINK_LIBRARIES(mrfstereo ${LIB_PNG} ${LIB_Z} libImg libMRF)  # libpng & zlib & libImg