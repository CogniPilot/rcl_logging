# SPDX-License-Identifier: Apache-2.0
if (CONFIG_RCL_LOGGING)

zephyr_library_named(rcl_logging)

target_compile_definitions(rcl_logging PUBLIC)

target_compile_options(rcl_logging PRIVATE -Wno-unused-variable -Wno-implicit-function-declaration -Wno-int-conversion)

zephyr_include_directories(
  ${ZEPHYR_CURRENT_MODULE_DIR}/rcl_logging_interface/include
  )

zephyr_library_include_directories(
  ${ZEPHYR_CURRENT_MODULE_DIR}/rcl_logging_interface/include
  )

file(GLOB_RECURSE Sources
  "${ZEPHYR_CURRENT_MODULE_DIR}/rcl_logging_interface/src/*.c"
)

#message(STATUS "Sources: ${Sources}")

zephyr_library_sources(
  ${Sources}
)

endif()
