add_executable(SPRoute main.cpp dist.c dl.c err.c heap.c mst2.c neighbors.c bookshelf_IO.c memAlloc.c)
add_dependencies(apps SPRoute)
target_link_libraries(SPRoute PRIVATE Galois::shmem lonestar)
install(TARGETS SPRoute DESTINATION "${CMAKE_INSTALL_BINDIR}" COMPONENT apps EXCLUDE_FROM_ALL)

add_test_scale(small1 SPRoute "${BASEINPUT}/eda/routing/test.gr" --flute "${BASEINPUT}/eda/routing")
