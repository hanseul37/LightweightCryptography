add_library(PRESENT STATIC present.c present.h id.h macros.h)
add_library(PRESENT_TEST STATIC test_present.c test_present.h)

target_include_directories(PRESENT_TEST PRIVATE ../../util)
target_link_libraries(PRESENT_TEST PRIVATE PRESENT)

# PRESENT_USE_KEY80, PRESENT_USE_KEY128
add_compile_definitions(PRESENT_USE_KEY128)

# 1~31
add_compile_definitions(PRESENT_ROUND_COUNT=10)