cmake_minimum_required(VERSION 3.10)

project(qtl866 VERSION 1.0.0 LANGUAGES CXX)

find_package(Qt5 COMPONENTS Widgets Core REQUIRED)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(HEADERS mainwindow.h
			optdialog.h
			devices.h
)

set(SOURCES main.cpp
			mainwindow.cpp
			optdialog.cpp
)

set(FORMS mainwindow.ui
		  optdialog.ui
)


add_executable(qtl866 ${SOURCES} ${HEADERS} ${FORMS})
target_link_libraries(qtl866 Qt::Widgets Qt::Core)

install(TARGETS qtl866 DESTINATION ${CMAKE_INSTALL_BINDIR}
        PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE)


