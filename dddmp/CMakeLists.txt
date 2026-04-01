set(DDDMP_C_HEADERS
  dddmp.h
  dddmpInt.h
)

set(DDDMP_C_SOURCES
  dddmpBinary.c
  dddmpNodeAdd.c
  dddmpStoreCnf.c
  dddmpConvert.c
  dddmpNodeBdd.c
  dddmpStoreMisc.c
  dddmpDbg.c
  dddmpNodeCnf.c
  dddmpUtil.c
  dddmpLoad.c
  dddmpStoreAdd.c
  dddmpLoadCnf.c
  dddmpStoreBdd.c
)

if (CUDD_SHARED)
  add_library(cudd_dddmp SHARED ${DDDMP_C_HEADERS} ${DDDMP_C_SOURCES})
else()
  add_library(cudd_dddmp STATIC ${DDDMP_C_HEADERS} ${DDDMP_C_SOURCES})
endif()

target_link_libraries(cudd_dddmp PRIVATE cudd_util cudd_st cudd_mtr cudd_epd cudd)

target_include_directories(cudd_dddmp PUBLIC ${CMAKE_CURRENT_BINARY_DIR}
                                        ${CMAKE_CURRENT_SOURCE_DIR})

set_target_properties(cudd PROPERTIES
  # Language settings
  LINKER_LANGUAGE C
  C_STANDARD 11
  C_STANDARD_REQUIRED ON

  # Linkage?
  FOLDER cudd

  # Other
  VERSION ${PROJECT_VERSION}
  POSITION_INDEPENDENT_CODE ON
)
