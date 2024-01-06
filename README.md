# docker-kubernetes-study

# Part 1

## 1. image 와 container 에 대한 개념

## 2. custom image build & run

## Summary

- Images are 'blueprints' for containers which then are running instances with read and write access.
- Having concepts of images and containers allows multiple containers to be based on the same image without interfering with each other.
- Isolation in the context of containers: containers are separated from each other and have no shared data or state by default.
- Container: an isolated unit of softward which is based on an image. A running instance of that image.
- Layers in the context of images: every instruction in an image creates a cacheable layer - layers help with image re-building and sharing.

--
