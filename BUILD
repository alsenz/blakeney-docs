load("@rules_pkg//:pkg.bzl", "pkg_tar")
load("@mkdocs_deps//:requirements.bzl", "requirement")
load("@rules_python//python:defs.bzl", "py_binary")
load("@rules_python//python/pip_install:requirements.bzl", "compile_pip_requirements")

genrule(
    name = "mkdocs_main",
    outs = ["mkdocs_main.py"],
    cmd = "echo -ne \"from mkdocs import __main__\n__main__.cli()\n\" > $@"
)

# To make this work, there is nothing you can do except go into external/mkdocs_deps_pypi__mkdocs_material_extensions/BUILD.bazel and make the extensions package _not_ depend on mkdocs-material to break the circular dependency...

py_binary(
    name = "mkdocs",
    deps = [
        requirement("mkdocs"),
        requirement("mkdocs-material")

    ],
    srcs = ["mkdocs_main.py"],
    main = "mkdocs_main.py",
    data = ["mkdocs.yml"] + glob(["docs/**/*.md"])
)

genrule(
    name = "mkdocs_package",
    srcs = ["mkdocs.yml"] + glob(["docs/**/*.md"]),
    outs = ["blakeney-docs.tar"],
    tools = [":mkdocs"],
    cmd = "./$(location :mkdocs) build -d mkdocs-out; pwd; tar -cvf $@ -C mkdocs-out ."
)



#TODO package up the docs

#container_image(
#    name = "blakeney_docs_img",
#    base = "@mkdocs_material",
#    tars = [":blakeney_docs_tar"]
#)
