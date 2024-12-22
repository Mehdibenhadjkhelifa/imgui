project(imgui)

# Collect ImGui source files
file(GLOB IMGUI_SOURCES
    #${CMAKE_CURRENT_SOURCE_DIR}/**.cpp
    #${CMAKE_CURRENT_SOURCE_DIR}/**.h
    imconfig.h imgui.h imgui.cpp imgui_draw.cpp imgui_internal.h
    imgui_tables.cpp imgui_widgets.cpp imstb_rectpack.h
    imstb_textedit.h imstb_truetype.h imgui_demo.cpp
)

# Add static library target
add_library(${PROJECT_NAME} STATIC ${IMGUI_SOURCES})

# Include directory
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# Dependencies
target_link_libraries(${PROJECT_NAME} PUBLIC glfw)

