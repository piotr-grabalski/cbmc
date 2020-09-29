set(test_pl_path "${CBMC_SOURCE_DIR}/../regression/test.pl")

if("${CMAKE_SYSTEM_NAME}" STREQUAL "Windows")
  message(WARNING "skipping broken jbmc tests on Windows")
else()
    # For the best possible utilisation of multiple cores when
    # running tests in parallel, it is important that these directories are
    # listed with decreasing runtimes (i.e. longest running at the top)
    add_subdirectory(jbmc)
    add_subdirectory(strings-smoke-tests)
    add_subdirectory(jbmc-strings)
    add_subdirectory(jdiff)
    add_subdirectory(janalyzer)
    add_subdirectory(janalyzer-taint)
    add_subdirectory(jbmc-concurrency)
    add_subdirectory(jbmc-inheritance)
    add_subdirectory(jbmc-generics)
    add_subdirectory(jbmc-json-ui)
endif()
