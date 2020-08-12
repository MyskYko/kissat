file(GLOB kissat_source_files "src/*.c")
list(REMOVE_ITEM kissat_source_files "src/main.c")
list(REMOVE_ITEM kissat_source_files "src/application.c")
list(REMOVE_ITEM kissat_source_files "src/handle.c")
list(REMOVE_ITEM kissat_source_files "src/parse.c")
list(REMOVE_ITEM kissat_source_files "src/witness.c")

add_library(kissat ${kissat_source_files})
target_include_directories(kissat PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src)
target_compile_options(kissat PRIVATE -DNEMBEDDED -DNMETRICS -DNSTATISTICS -DNPROOFS -DQUIET -DCOMPACT)

