if(("${CMAKE_VERSION}" VERSION_GREATER 3.8.0) OR ("${CMAKE_VERSION}" VERSION_EQUAL 3.8.0))
    app(sweeps sweeps.cpp)
else()
    message(WARNING "Cannot configure sweeps or other C++17 apps with a CMake version older than 3.8. Skipping.")
endif()

