project('outputs not matching install_dirs', 'c')

gen = find_program('generator.py')

if meson.backend() != 'ninja'
  error('Failing manually, test is only for the ninja backend')
endif

custom_target('too-few-install-dirs',
  output : ['toofew.h', 'toofew.c', 'toofew.sh'],
  command : [gen, 'toofew', '@OUTDIR@'],
  install : true,
  install_dir : [join_paths(get_option('prefix'), get_option('includedir')), false])
