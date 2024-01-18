# docker-kubernetes-study

# Part 1

### 1. image 와 container 에 대한 개념

### 2. custom image build & run

## Part 1. Summary

- Images are 'blueprints' for containers which then are running instances with read and write access.
- Having concepts of images and containers allows multiple containers to be based on the same image without interfering with each other.
- Isolation in the context of containers: containers are separated from each other and have no shared data or state by default.
- Container: an isolated unit of softward which is based on an image. A running instance of that image.
- Layers in the context of images: every instruction in an image creates a cacheable layer - layers help with image re-building and sharing.

  
# Part 2. Managing Images & Containers
### Docker 명령어 정리
- `docker images` 이미지 조회
- `docker pull [이미지 이름]:[태그]` 이미지 가져오기 (from dockerHub)
- `docker build <옵션> <Dockerfile 경로>` 이미지 생성
- `docker rmi [이미지 id]` 이미지 삭제
- `docker ps` 실행중인 컨테이너 목록 조회


### Docker 옵션 정리
- `-d` detached mode
- `-p` 호스트와 컨테이너의 포트 연결 (포워딩)
- `-v` 호스트와 컨테이너의 디렉토리 연결 (named volume 관련)
- `--name` 컨테이너의 이름 설정
- `--it` 컨테이너와의 I/O 인터랙션 가능하게 설정 (터미널 입력을 위한 옵션)
- `--rm` 프로세스(컨테이너) 종료 혹은 중단(stop) 시 컨테이너 자동 제거


# Part 3. Volumes & Bind Mounts
- `Volume` is a folder / file inside of Docker container which is connected to some folder outside of the container. Volumes are managed by Docker, you don't necessarily know where the host folder (which is mapped to a container-internal path) is.
- `Anonymous Volumes` are only auto-removed if the container was started with the `--rm` option. However you can use them to prioritize container-internal paths higher than external paths.
- `Named Volumes` survive container removal.
- `Bind Mount` is a path on your host machine, which you know and specified, that is mapped to some container-internal path. It is typically used when you want to provide "live data" to the container (no rebuilding needed).
