cmake_minimum_required(VERSION 2.8)

project (ImGui)

add_library(ImGuiImpl OBJECT ${PROJECT_SOURCE_DIR}/imgui_impl)
target_include_directories(ImGuiImpl PRIVATE ${PROJECT_SOURCE_DIR})
set_target_properties(ImGuiImpl PROPERTIES LINKER_LANGUAGE Cxx)

aux_source_directory(${PROJECT_SOURCE_DIR} SRC_LIST)


add_library(ImGui STATIC ${SRC_LIST} $<TARGET_OBJECTS:ImGuiImpl>)
