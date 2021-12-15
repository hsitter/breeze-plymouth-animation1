set(DISTRO_LOGO "plasma" CACHE STRING "Image filename to use on splash screen")
set(BACKGROUND_TOP_COLOR "black" CACHE STRING "Color for top of splash screen")
set(BACKGROUND_BOTTOM_COLOR "black" CACHE STRING "Color for bottom of splash screen")

add_feature_info(DISTRO_LOGO On "image filename to use on splash screen is '${DISTRO_LOGO}'")
add_feature_info(BACKGROUND_TOP_COLOR On "Color for top of splash screen is '${BACKGROUND_TOP_COLOR}'")
add_feature_info(BACKGROUND_BOTTOM_COLOR On "Color for bottom of splash screen is '${BACKGROUND_BOTTOM_COLOR}'")

configure_file(neon-shrink.plymouth.cmake ${CMAKE_CURRENT_BINARY_DIR}/neon-shrink.plymouth)
configure_file(neon-shrink.script.cmake ${CMAKE_CURRENT_BINARY_DIR}/neon-shrink.script)

install(FILES neon-shrink.grub
              preview.png
              ${CMAKE_CURRENT_BINARY_DIR}/neon-shrink.script
              ${CMAKE_CURRENT_BINARY_DIR}/neon-shrink.plymouth
        DESTINATION ${Plymouth_THEMESDIR}/neon-shrink)
install(DIRECTORY images
        DESTINATION ${Plymouth_THEMESDIR}/neon-shrink)
