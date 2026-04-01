set(ST_C_HEADERS
  st.h
)

set(ST_C_SOURCES
  st.c
  #testst.c
)

add_library(cudd_st STATIC ${ST_C_HEADERS} ${ST_C_SOURCES})

target_link_libraries(cudd_st PRIVATE cudd_util)

target_include_directories(cudd_st PUBLIC ${CMAKE_CURRENT_BINARY_DIR}
                                     ${CMAKE_CURRENT_SOURCE_DIR})
