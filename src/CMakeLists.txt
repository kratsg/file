configure_file(magic.h.in magic.h)

add_library(libmagic SHARED
  buffer.c magic.c magic.h apprentice.c softmagic.c ascmagic.c
  encoding.c compress.c is_csv.c is_json.c is_tar.c readelf.c print.c
  fsmagic.c funcs.c file.h readelf.h tar.h apptype.c der.c der.h
  file_opts.h elfclass.h mygetopt.h cdf.c cdf_time.c readcdf.c cdf.h
)

add_library(file SHARED
  file.c seccomp.c
)
