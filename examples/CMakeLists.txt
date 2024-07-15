# Generated from examples.pro.

find_package(Qt6 ${PROJECT_VERSION} CONFIG OPTIONAL_COMPONENTS Multimedia) # special case

qt_examples_build_begin()

if(WIN32)
    add_subdirectory(winextras)
endif()

qt_examples_build_end()
