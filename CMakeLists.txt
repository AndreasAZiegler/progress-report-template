cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/")
INCLUDE(pandocology)

add_document(
    TARGET progressreport
    OUTPUT_FILE progressreport.pdf
    SOURCES progressreport.md
    RESOURCE_FILES progressreport.bib ./subtitle.tex ./ieee.csl
    PANDOC_DIRECTIVES --citeproc
                      --bibliography progressreport.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
