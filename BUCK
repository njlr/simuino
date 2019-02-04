genrule(
  name = 'ncurses-h',
  out = 'ncurses.h',
  cmd = 'cp /usr/include/ncurses.h $OUT',
)

prebuilt_cxx_library(
  name = 'ncurses',
  header_only = True,
  exported_headers = {
    'ncurses.h': ':ncurses-h',
  },
  exported_linker_flags = [
    '-lncurses',
  ],
)

cxx_binary(
  name = 'simuino',
  header_namespace = '',
  headers = glob([
    'simuino.h',
    'simuino_lib.c',
    'servuino/*.h',
    'servuino/common_lib.c',
  ]),
  srcs = [
    'simuino.cpp',
  ],
  licenses = [
    'gpl.txt',
  ],
  deps = [
    '//:ncurses',
  ],
  visibility = [
    'PUBLIC',
  ],
)
