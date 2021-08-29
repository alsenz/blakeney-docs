load("@rules_pkg//:pkg.bzl", "pkg_tar")

load("@pip//:requirements.bzl", "requirement")
load("@rules_python//python:defs.bzl", "py_binary")
load("@rules_python//python/pip_install:requirements.bzl", "compile_pip_requirements")

genrule(
    name = "mkdocs_main",
    outs = ["mkdocs_main.py"],
    cmd = "echo -ne \"from mkdocs import __main__\n__main__.cli()\n\" > $@"
)

py_binary(
    name = "mkdocs",
    deps = [
        requirement("mkdocs"),
        requirement("mkdocs-gitbook")
    ],
    srcs = ["mkdocs_main.py"],
    main = "mkdocs_main.py",
    data = ["mkdocs.yml"] + glob(["docs/*.md"])
)

#TODO let's do a sh_binary



#TODO package up the docs

#container_image(
#    name = "blakeney_docs_img",
#    base = "@mkdocs_material",
#    tars = [":blakeney_docs_tar"]
#)
