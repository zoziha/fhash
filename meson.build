project(
    'fhash',
    'fortran',
    version : '0.1.0',
    default_options: [
        'buildtype=debugoptimized',
        'fortran_std=f2008',
        'default_library=both',
    ]
)

subdir('src')
subdir('app')
subdir('test')

fhash_lic = files(
    'LICENSE',
)
install_data(
    fhash_lic,
    install_dir: get_option('datadir')/'licenses'/meson.project_name(),
)
