find_package(glfw3)

add_library(
    imgui STATIC
    imgui.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    imgui_demo.cpp
    imgui_impl_glfw.h
    imgui_impl_glfw.cpp
    imgui_impl_opengl3.h
    imgui_impl_opengl3.cpp
)

target_link_libraries(imgui PRIVATE glfw)
