cmake_minimum_required(VERSION 3.16)
project(ShuangpinHintTests LANGUAGES CXX)
find_package(Fcitx5Utils REQUIRED CONFIG)
find_package(LibIMEPinyin REQUIRED CONFIG)
add_executable(testshuangpinkeyhints
    ../im/pinyin/shuangpinkeyhints.cpp
    ../test/testshuangpinkeyhints.cpp)
target_compile_features(testshuangpinkeyhints PRIVATE cxx_std_20)
target_link_libraries(testshuangpinkeyhints PRIVATE Fcitx5::Utils LibIME::Pinyin)
enable_testing()
add_test(NAME shuangpin-key-hints COMMAND testshuangpinkeyhints)
