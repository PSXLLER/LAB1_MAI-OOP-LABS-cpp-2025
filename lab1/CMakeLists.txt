cmake_minimum_required(VERSION 3.22)
project(lab1)

set(CMAKE_CXX_STANDARD 20)

add_executable(palindrome_app palindrome_app.cpp palindrome.cpp)

enable_testing()

include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/refs/tags/v1.14.0.zip
)
FetchContent_MakeAvailable(googletest)

add_executable(palindrome_test palindrome_test.cpp palindrome.cpp)
target_link_libraries(palindrome_test gtest gtest_main pthread)

add_test(NAME PalindromeTests COMMAND palindrome_test)
