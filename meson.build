project('TheCatacomb', 'c')

compiler = meson.get_compiler('c')

if not compiler.has_function('stricmp')
	add_project_arguments('-Dstricmp=strcasecmp', language : 'c')
endif

if not compiler.has_function('strnicmp')
	add_project_arguments('-Dstrnicmp=strncasecmp', language : 'c')
endif

sdl2 = dependency('sdl2')

if compiler.get_id() == 'msvc'
	add_project_arguments('/wd4996', language : 'c')
else 
	add_project_arguments('-Wall', '-Wno-unused-result', language : 'c')
	add_project_arguments('-Wall', '-Wno-unused-result', language : 'cpp')
endif

src = [
	'cat_play.c', 
	'catacomb.c', 
	'catasm.c', 
	'cpanel.c', 
	'objects.c', 
	'pcrlib_a.c', 
	'pcrlib_c.c', 
	'rleasm.c']

executable('catacomb', sources : src, dependencies : sdl2)