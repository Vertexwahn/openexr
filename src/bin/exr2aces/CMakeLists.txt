# SPDX-License-Identifier: BSD-3-Clause
# Copyright (c) Contributors to the OpenEXR Project.

add_executable(exr2aces main.cpp)
target_link_libraries(exr2aces OpenEXR::OpenEXR)
set_target_properties(exr2aces PROPERTIES
  RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
if(OPENEXR_INSTALL_TOOLS)
  install(TARGETS exr2aces DESTINATION ${CMAKE_INSTALL_BINDIR})
endif()
if(WIN32 AND BUILD_SHARED_LIBS)
  target_compile_definitions(exr2aces PRIVATE OPENEXR_DLL)
endif()
