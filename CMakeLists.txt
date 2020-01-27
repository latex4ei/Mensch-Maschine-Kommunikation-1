cmake_minimum_required(VERSION 2.8)

project(MMK1 NONE)
include(UseLATEX)

add_custom_target(
    writegitid ALL
    COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/write-gitid.sh
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)

add_latex_document(
    mmk1.tex
    FORCE_PDF
    IMAGE_DIRS img img/old
    DEPENDS writegitid
)

add_latex_document(
    mmk1_vor_ws16-17.tex
    FORCE_PDF
    IMAGE_DIRS img img/old
    DEPENDS writegitid
)
