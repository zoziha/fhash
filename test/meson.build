source_files = files(
    'test_container.f90',
    'test_fnv.f90',
    'test_key.f90',
    'test_sll.f90',
    'test_tbl_iter.f90',
    'test_tbl.f90',
    'TestLite_error.f90',
    'TestLite_suite.f90',
    'TestLite.f90',
)

test_lib = static_library(
    'test-lib',
    sources: source_files,
    link_with: fhash_lib,
)

test(
    'tester',
    executable(
        'tester',
        'main.f90',
        link_with: test_lib,
    )
)
