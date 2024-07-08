# The following lines of boilerplate have to be in your project's CMakeLists
# in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.5)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)

# set the path to the parent directory of the component
set(COMPONENT_PARENT_DIR "../../")

# if ESPP_DIR is not set, set it to the default location (which assumes espp is
# a sibling of the component)
if(NOT DEFINED ESPP_DIR)
  set(ESPP_DIR "${COMPONENT_PARENT_DIR}/espp")
endif()

# add the component directories that we want to use
set(EXTRA_COMPONENT_DIRS
  "${COMPONENT_PARENT_DIR}/espp_gfps_service"
  "${ESPP_DIR}/components"
)

set(
  COMPONENTS
  "main esptool_py ble_gatt_server espp_gfps_service"
  CACHE STRING
  "List of components to include"
  )

project(espp_gfps_service_example)

set(CMAKE_CXX_STANDARD 20)
