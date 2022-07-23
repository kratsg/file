add_library(magic SHARED
            Makefile.am
)

set(MAGIC_FRAGMENT_BASE Magdir)
set(MAGIC_DIR ${PROJECT_SOURCE_DIR}/magic)
set(MAGIC_FRAGMENT_DIR ${MAGIC_DIR}/${MAGIC_FRAGMENT_BASE})
set(pkgdata_DATA magic.mgc)

file(GLOB MAGIC_FRAGMENTS
          CONFIGURE_DEPENDS
          "${MAGIC_DIR}/Header"
          "${MAGIC_DIR}/Localstuff"
          "${MAGIC_FRAGMENT_DIR}/*"
)

file(GLOB EXTRA_DIST
          "${MAGIC_DIR}/scripts/create_filemagic_flac"
          "${MAGIC_FRAGMENTS}"
)

if (WIN32)
	# Automake calls this EXEEXT, and CMake doesn't have a standard name
	# for it; follow Automake's naming convention so we can share .in files
	set (EXEEXT ".exe")
endif(WIN32)
