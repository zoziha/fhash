source_files = [
    'fhash_data_container.f90',
    'fhash_fnv.f90',
    'fhash_sll.f90',
    'fhash_tbl_iter.f90',
    'fhash_tbl.f90',
    'fhash.f90',
]

subdir('fhash_key')

fhash_lib = library(
    meson.project_name(),
    sources: files(source_files)+fhash_key_src,
    version: meson.project_version(),
    install: true,
)

fhash_inc = fhash_lib.private_dir_include()
fhash_dep = declare_dependency(
    include_directories: fhash_inc,
    link_with: fhash_lib,
)

if host_machine.system() == 'windows'
    symbols_file = 'lib'+meson.project_name()+'-'+meson.project_version().split('.')[0]+'.dll.symbols'
    obj_suffix = '.obj'
else
    symbols_file = 'lib'+meson.project_name()+'.so.'+meson.project_version()+'.symbols'
    obj_suffix = '.o'
endif

objs = []
foreach source: source_files
    objs += source+obj_suffix
endforeach
foreach source: fhash_key_source_files
    objs += 'fhash_key_'+source+obj_suffix
endforeach

install_subdir(fhash_lib.path()+'.p',
    install_dir: 'include'/meson.project_name(),
    strip_directory: true,
    exclude_files: [
        'depscan.dd',
        meson.project_name()+'-deps.json',
        symbols_file,
        meson.project_name()+'.dat',
        objs,
    ]
)

pkg = import('pkgconfig')
pkg.generate(
    fhash_lib,
    name: meson.project_name(),
    description: 'Fortran free function collection',
    version: meson.project_version(),
    subdirs: meson.project_name(),
)