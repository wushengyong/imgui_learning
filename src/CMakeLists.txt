cmake_minimum_required(VERSION 2.8)

project (12306Magic)

add_subdirectory(3rd_party/imgui)

aux_source_directory(${PROJECT_SOURCE_DIR} SRC_LIST)

add_executable(12306Magic ${SRC_LIST})

set (THIRD_PARTY_PATH ${PROJECT_SOURCE_DIR}/3rd_party)

set (IMGUI_SRC_PATH ${THIRD_PARTY_PATH}/ImGui)
set (IMGUI_INC_PATH ${IMGUI_SRC_PATH} ${IMGUI_SRC_PATH}/imgui_impl)

message (STATUS "正在处理ImGui，路径" ${IMGUI_INC_PATH})

target_include_directories(12306Magic PRIVATE ${IMGUI_INC_PATH})
target_link_libraries(12306Magic ImGui)
