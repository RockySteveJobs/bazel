# Description:
#   Tests for the checker to check the completeness of the deps of java_import or aar_import targets.
package(
    default_testonly = 1,
    default_visibility = ["//src:__subpackages__"],
)

filegroup(
    name = "srcs",
    testonly = False,
    srcs = glob(["**"]) + ["//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:srcs"],
)

java_test(
    name = "ClassInfoTest",
    srcs = ["ClassInfoTest.java"],
    deps = [
        "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:import_deps_checker",
        "//third_party:guava",
        "//third_party:junit4",
        "//third_party:truth",
    ],
)

java_test(
    name = "ResultCollectorTest",
    srcs = ["ResultCollectorTest.java"],
    deps = [
        "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:import_deps_checker",
        "//third_party:guava",
        "//third_party:junit4",
        "//third_party:truth",
    ],
)

java_test(
    name = "LazyClassEntryStateTest",
    srcs = ["LazyClassEntryStateTest.java"],
    deps = [
        "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:import_deps_checker",
        "//src/test/java/com/google/devtools/build/lib:testutil",
        "//third_party:guava",
        "//third_party:junit4",
        "//third_party:truth",
    ],
)

java_test(
    name = "ClassCacheTest",
    srcs = [
        "AbstractClassCacheTest.java",
        "ClassCacheTest.java",
    ],
    data = [
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_client",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_Library",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryAnnotations",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryException",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryInterface",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_Library_no_members",
        "@local_jdk//:jre/lib/rt.jar",
    ],
    jvm_flags = [
        "-Dclasscache.test.bootclasspath=$(location @local_jdk//:jre/lib/rt.jar)",
        "-Dclasscache.test.Client=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_client)",
        "-Dclasscache.test.Library=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_Library)",
        "-Dclasscache.test.Library_no_members=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_Library_no_members)",
        "-Dclasscache.test.LibraryAnnotations=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryAnnotations)",
        "-Dclasscache.test.LibraryException=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryException)",
        "-Dclasscache.test.LibraryInterface=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryInterface)",
    ],
    test_class = "com.google.devtools.build.importdeps.ClassCacheTest",
    deps = [
        "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:import_deps_checker",
        "//src/test/java/com/google/devtools/build/lib:testutil",
        "//third_party:guava",
        "//third_party:junit4",
        "//third_party:truth",
    ],
)

java_test(
    name = "DepsCheckerClassVisitorTest",
    srcs = [
        "AbstractClassCacheTest.java",
        "DepsCheckerClassVisitorTest.java",
    ],
    data = [
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_client",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_Library",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryAnnotations",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryException",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryInterface",
        "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_Library_no_members",
        "@local_jdk//:jre/lib/rt.jar",
    ],
    jvm_flags = [
        "-Dclasscache.test.bootclasspath=$(location @local_jdk//:jre/lib/rt.jar)",
        "-Dclasscache.test.Client=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_client)",
        "-Dclasscache.test.Library=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_Library)",
        "-Dclasscache.test.Library_no_members=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_Library_no_members)",
        "-Dclasscache.test.LibraryAnnotations=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryAnnotations)",
        "-Dclasscache.test.LibraryException=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryException)",
        "-Dclasscache.test.LibraryInterface=$(location //src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata:testdata_lib_LibraryInterface)",
    ],
    test_class = "com.google.devtools.build.importdeps.DepsCheckerClassVisitorTest",
    deps = [
        "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:import_deps_checker",
        "//third_party:asm",
        "//third_party:guava",
        "//third_party:junit4",
        "//third_party:truth",
        "@local_jdk//:jre/lib/rt.jar",
    ],
)

load("//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps:tests.bzl", "create_golden_test")

create_golden_test(
    name = "bootclasspath_missing_golden_test",
    golden_file = "golden_bootclasspath_missing.txt",
    has_bootclasspath = False,
    import_deps_checker = "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:ImportDepsChecker",
    missing_jar = None,
    rt_jar = "@local_jdk//:jre/lib/rt.jar",
    testdata_pkg = "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata",
)

create_golden_test(
    name = "library_exception_missing_golden_test",
    golden_file = "golden_library_exception_missing.txt",
    has_bootclasspath = True,
    import_deps_checker = "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:ImportDepsChecker",
    missing_jar = "testdata_lib_LibraryException",
    rt_jar = "@local_jdk//:jre/lib/rt.jar",
    testdata_pkg = "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata",
)

create_golden_test(
    name = "library_annotation_missing_golden_test",
    golden_file = "golden_library_annotation_missing.txt",
    has_bootclasspath = True,
    import_deps_checker = "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:ImportDepsChecker",
    missing_jar = "testdata_lib_LibraryAnnotations",
    rt_jar = "@local_jdk//:jre/lib/rt.jar",
    testdata_pkg = "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata",
)

create_golden_test(
    name = "library_missing_golden_test",
    golden_file = "golden_library_missing.txt",
    has_bootclasspath = True,
    import_deps_checker = "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:ImportDepsChecker",
    missing_jar = "testdata_lib_Library",
    rt_jar = "@local_jdk//:jre/lib/rt.jar",
    testdata_pkg = "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata",
)

create_golden_test(
    name = "library_interface_missing_golden_test",
    golden_file = "golden_library_interface_missing.txt",
    has_bootclasspath = True,
    import_deps_checker = "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:ImportDepsChecker",
    missing_jar = "testdata_lib_LibraryInterface",
    rt_jar = "@local_jdk//:jre/lib/rt.jar",
    testdata_pkg = "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata",
)

create_golden_test(
    name = "library_members_missing_golden_test",
    golden_file = "golden_library_members_missing.txt",
    has_bootclasspath = True,
    import_deps_checker = "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:ImportDepsChecker",
    missing_jar = "testdata_lib_Library",
    replacing_jar = "testdata_lib_Library_no_members",
    rt_jar = "@local_jdk//:jre/lib/rt.jar",
    testdata_pkg = "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata",
)

create_golden_test(
    name = "complete_classpath_golden_test",
    golden_file = "golden_complete_classpath.txt",
    has_bootclasspath = True,
    import_deps_checker = "//src/java_tools/import_deps_checker/java/com/google/devtools/build/importdeps:ImportDepsChecker",
    missing_jar = None,
    replacing_jar = None,
    rt_jar = "@local_jdk//:jre/lib/rt.jar",
    testdata_pkg = "//src/java_tools/import_deps_checker/javatests/com/google/devtools/build/importdeps/testdata",
)
