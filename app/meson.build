executable(
    'bench',
    'bench/main.f90',
    link_with: fhash_lib,
)

executable(
    'iter-demo',
    '4-iter-demo/main.f90',
    link_with: fhash_lib,
)

executable(
    'custom-key-demo',
    ['3-custom-key-demo/main.f90', '3-custom-key-demo/my_key_type.f90',],
    link_with: fhash_lib,
)

executable(
    'drived-type-demo',
    '2-drived-type-demo/main.f90',
    link_with: fhash_lib,
)

executable(
    'methods-demo',
    '1-methods-demo/main.f90',
    link_with: fhash_lib,
)

executable(
    'simple-demo',
    '0-simple-demo/main.f90',
    link_with: fhash_lib,
)
