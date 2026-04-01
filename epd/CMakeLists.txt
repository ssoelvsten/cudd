set(EPD_C_HEADERS
  epd.h
  epdInt.h
)

set(EPD_C_SOURCES
  epd.c
)

add_library(cudd_epd STATIC ${EPD_C_HEADERS} ${EPD_C_SOURCES})

target_link_libraries(cudd_epd PRIVATE cudd_util)

target_include_directories(cudd_epd PUBLIC ${CMAKE_CURRENT_BINARY_DIR}
                                      ${CMAKE_CURRENT_SOURCE_DIR})
