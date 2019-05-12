cmake_minimum_required(VERSION 3.1.0)

project(QPickit2)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

find_package(Qt5Widgets CONFIG REQUIRED)
find_package(Qt5Core REQUIRED)
find_package(Qt5Gui REQUIRED)



set(QPickit2_SRCS
    mainwindow.ui
    mainwindow.cpp
    main.cpp
    worker.cpp
    img/img.qrc
)

add_executable(QPickit2 WIN32 ${QPickit2_SRCS})
target_link_libraries(QPickit2 Qt5::Widgets)

INSTALL( DIRECTORY img DESTINATION /opt/qpickit2 )
INSTALL(TARGETS QPickit2 DESTINATION /opt/qpickit2 COMPONENT binaries)
INSTALL(FILES QPickit2.desktop DESTINATION /usr/share/applications)
