cmake_minimum_required(VERSION 3.10)
project(KediPlazma-darkalpha_1.0)

set(CMAKE_CXX_STANDARD 17)

find_package(PkgConfig REQUIRED)
pkg_check_modules(WAYLAND REQUIRED wayland-client wayland-server)
pkg_check_modules(WLROOTS REQUIRED wlroots)

# src klasöründeki dosyayı doğrudan burada tanımla
add_executable(kedi-plazma src/main.cpp)

# Kütüphaneleri bağla
target_link_libraries(kedi-plazma 
    ${WAYLAND_LIBRARIES} 
    ${WLROOTS_LIBRARIES}
)
