# Base Tagged Images For My Docker Projects

This is a set of tagged images for my Docker images.  It only adds `LABEL` to a given primary image.

These tagged images make it easier for myself to update my other images without updating those repositories or triggering a rebuild directly of those images.  It also gives each of my images the `LABEL` as well, which does not add any files/content to the image, but does add to the metadata of the final image.

These base images should not be used for your own Docker images, as they only provide a base `LABEL` (currently just a `maintainer` and a `github` label), but you may use this format/idea for your own projects.

## Image Tags

Below is a list of my current base image tags used for my Docker projects.

* scratch (used in place of "FROM scratch" in Docker images)
* alpine
* busybox
* golang
* node
* python3

The above are the tags available for the `macgyverbass/base-label` image.  There is no `latest` tag for this image.

## Notes

In each of my base images, I use Alpine to keep the image size as small as possible and use the major/minor version number for Alpine to prevent my images from breaking when the major or minor version number updates, which may happen when packages from the newer repository are updated in such a way that may break package installation/usage.

If you decide to create your own base tagged images like this project, you may choose to use images that leave out the minor version or both the major & minor version, or you may even choose to use a different base image for your projects (e.g. debian or ubuntu).  If you do so, I recommend testing your projects and verifying that they do not break if/when a base image does a major update.

## Summary

This project was designed to help me keep all my projects up-to-date and organized by label when I review them locally.  Again, please avoid using my base tagged images in your own projects and instead either create your own tagged base images with personalized labels or use the official base images themselves for your projects.  While my images do not modify any files or add any code to the base image currently, I will only be updating these tagged images online after I've tested my other projects on my local machine.
