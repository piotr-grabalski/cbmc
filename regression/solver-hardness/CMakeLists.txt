if(NOT "${CMAKE_SYSTEM_NAME}" STREQUAL "Windows")
  add_test_pl_tests(
    "../chain.sh $<TARGET_FILE:cbmc>")
else()
  message(WARNING "skipping known problematic test on windows")
endif()