<!-- .slide: data-state="normal" id="branch-images" data-menu-title="Create and use your first image" -->
# Create and use your first image in kanku

```
osc branch devel:kanku:images openSUSE-Tumbleweed-JeOS
osc r -w home:<user>:branches:devel:kanku:images openSUSE-Tumbleweed-JeOS
```

```
# In KankuFile:
```
```
  -
    module: Kanku:Handler:OBSCheck
    project: home:<user>:branches:devel:kanku:images
    package: openSUSE-Tumbleweed-JeOS
    repository: images_tumbleweed
    ...
```
