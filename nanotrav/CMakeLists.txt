set(NANOTRAV_C_HEADERS
  bnet.h
  ntr.h
)

set(NANOTRAV_C_SOURCES
  bnet.c
  chkMterm.c
  ntr.c
  ntrBddTest.c
  ntrHeap.c
  ntrMflow.c
  ntrShort.c
  ntrZddTest.c
  main.c
)

add_executable(cudd_nanotrav ${NANOTRAV_C_HEADERS} ${NANOTRAV_C_SOURCES})
target_link_libraries(cudd_nanotrav PRIVATE cudd_epd cudd_mtr cudd_st cudd cudd_util cudd_dddmp)
