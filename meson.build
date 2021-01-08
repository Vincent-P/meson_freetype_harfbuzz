project('text', 'cpp', default_options : ['default_library=static', 'buildtype=debug', 'cpp_std=c++17', 'wrap_mode=nopromote'])

links = []
deps = []

freetype2_proj = subproject('freetype2', default_options: ['harfbuzz=disabled'])
freetype2_dep = freetype2_proj.get_variable('freetype2_dep')

harfbuzz_proj = subproject('harfbuzz', default_options: ['default_library=static', 'freetype=enabled', 'cairo=disabled', 'glib=disabled'])
harfbuzz_dep = harfbuzz_proj.get_variable('libharfbuzz_dep')
deps += harfbuzz_dep

freetype2_harfbuzz_proj = subproject('freetype2_harfbuzz', default_options: ['default_library=static', 'harfbuzz=enabled'])
freetype2_harfbuzz_dep = freetype2_proj.get_variable('freetype2_dep')
deps += freetype2_harfbuzz_dep

executable('text', 'main.cc', link_with: links, dependencies: deps)
