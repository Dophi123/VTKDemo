CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

set(NAME vtkNiftiDemo)
PROJECT(${NAME})

set(VTK_DIR D:/VTK_Install/8.2/VS2015x64/lib/cmake/vtk-8.2/)

find_package(VTK REQUIRED)
include(${VTK_USE_FILE})
message(${VTK_USE_FILE})

include_directories(     
    ${CMAKE_CURRENT_BINARY_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}
)

SET(Hdrs 
)

SET(Srcs	
main.cpp
)

add_definitions(-DmyDisableOpenJPEG)
ADD_EXECUTABLE(${NAME} ${Hdrs} ${Srcs})
target_link_libraries(${NAME}  ${VTK_LIBRARIES})