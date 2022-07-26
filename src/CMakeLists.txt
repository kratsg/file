set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

include(ConfigureChecks)

add_library(libmagic SHARED
  buffer.c magic.c magic.h apprentice.c softmagic.c ascmagic.c
  encoding.c compress.c is_csv.c is_json.c is_tar.c readelf.c print.c
  fsmagic.c funcs.c file.h readelf.h tar.h apptype.c der.c der.h
  file_opts.h elfclass.h mygetopt.h cdf.c cdf_time.c readcdf.c cdf.h
)
target_compile_definitions(libmagic PUBLIC HAVE_CONFIG_H=1)
target_include_directories(libmagic PUBLIC ${CMAKE_CURRENT_BINARY_DIR})

add_executable(file file.c magic.c)

target_compile_definitions(file PUBLIC HAVE_CONFIG_H=1)
target_include_directories(file PUBLIC ${CMAKE_CURRENT_BINARY_DIR})
target_link_libraries(file magic)
