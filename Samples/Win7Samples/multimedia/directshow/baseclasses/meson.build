sources = [
  'amextra.cpp',
  'amfilter.cpp',
  'amvideo.cpp',
  'arithutil.cpp',
  'combase.cpp',
  'cprop.cpp',
  'ctlutil.cpp',
  'ddmm.cpp',
  'dllentry.cpp',
  'dllsetup.cpp',
  'mtype.cpp',
  'outputq.cpp',
  'perflog.cpp',
  'pstream.cpp',
  'pullpin.cpp',
  'refclock.cpp',
  'renbase.cpp',
  'schedule.cpp',
  'seekpt.cpp',
  'source.cpp',
  'strmctl.cpp',
  'sysclock.cpp',
  'transfrm.cpp',
  'transip.cpp',
  'videoctl.cpp',
  'vtrans.cpp',
  'winctrl.cpp',
  'winutil.cpp',
  'wxdebug.cpp',
  'wxlist.cpp',
  'wxutil.cpp',
]

strmiids_lib = cxx.find_library('strmiids', required: true)
winmm_lib = cxx.find_library('winmm', required: true)

args = ['-DWINVER=0x0601', '-DFILTER_DLL']
if get_option('debug')
  library_name = 'strmbasd'
  args += ['-DDEBUG']
else
  library_name = 'strmbase'
  args += ['-DNDEBUG']
endif

dshow_strmbase_lib = library(library_name, sources,
  cpp_args: args,
  dependencies: [strmiids_lib, winmm_lib],
  install: true)
  
dshow_strmbase_dep = declare_dependency(link_with: dshow_strmbase_lib,
  include_directories: include_directories('.'))
