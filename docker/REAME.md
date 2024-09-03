# Docker

- 컨테이너를 사용해 애플리케이션을 신속하게 구축, 테스트 및 배포할 수 있는 소프트웨어 플랫폼

## Contaner?

- 컨테이너는 애플리케이션과 그에 필요한 모든 종속성(라이브러리, 구성 파일, 시스템 도구 등)을 포함하는 가벼운 독립 실행 환경입니다. 
- 이 환경은 다른 애플리케이션과 격리된 상태로 운영되며, 동일한 호스트 운영 체제(OS) 위에서 동작하지만, 서로의 영향을 받지 않습니다.

## Docker container

- Docker 컨테이너는 애플리케이션과 그에 필요한 모든 환경을 독립적으로 실행할 수 있는 경량화된 가상화 기술입니다.
- Docker 컨테이너는 운영 체제 수준에서의 가상화 기술로, 동일한 호스트 운영 체제 커널을 공유하면서도 애플리케이션을 격리된 공간에서 실행할 수 있습니다. 
- 각 컨테이너는 독립된 환경을 제공하며, 필요한 모든 요소가 포함되어 있어 특정 환경에 종속되지 않고 일관된 실행이 가능합니다.


## Dockerfile

- Dockerfile은 Docker 이미지를 생성하기 위한 일종의 청사진(설계도) 역할을 합니다. 
- 이 파일은 Docker 이미지를 빌드하는 데 필요한 모든 명령어, 구성 정보, 종속성을 포함하며, 텍스트 기반의 파일로 작성됩니다. 

1. 이미지 빌드 자동화

    - Dockerfile은 일련의 명령어로 구성되어 있으며, 이를 통해 이미지 빌드 과정을 자동화할 수 있습니다. 
    - 개발자는 Dockerfile에 필요한 설정과 명령어를 작성해 두면, 언제든지 동일한 이미지를 일관성 있게 재생산할 수 있습니다. 
    - 이 자동화된 프로세스는 수작업의 실수를 줄이고, 이미지 빌드의 일관성을 보장합니다.

1. 환경 설정 및 종속성 관리

    - Dockerfile은 애플리케이션이 실행되는 환경을 설정하는 데 사용됩니다. 
    - 예를 들어, 필요한 운영 체제, 시스템 라이브러리, 애플리케이션의 런타임 환경(예: Node.js, Python, Java 등) 등을 명시할 수 있습니다. 
    - 이를 통해 개발, 테스트, 프로덕션 환경 간의 차이를 최소화할 수 있습니다.
    - RUN, COPY, ADD 등의 명령어를 사용하여 종속성을 설치하고 파일을 복사함으로써 애플리케이션이 원활히 동작하는 데 필요한 모든 요소를 Docker 이미지 안에 포함시킬 수 있습니다.

1. 재현 가능한 배포

    - Dockerfile을 사용하면 특정 버전의 소프트웨어, 환경 설정, 패키지 버전을 고정하여 동일한 이미지를 언제든지 재생성할 수 있습니다. 
    - 이는 소프트웨어 배포 시 발생할 수 있는 'Works on my machine' 문제를 해결하는 데 크게 기여합니다. 
    - 모든 개발자가 동일한 Dockerfile을 사용해 동일한 환경에서 작업할 수 있기 때문입니다.

1. 애플리케이션 포팅

    - Dockerfile을 사용하면 애플리케이션을 하나의 환경에서 다른 환경으로 쉽게 포팅할 수 있습니다. 
    - Dockerfile에 정의된 내용은 운영 체제나 호스트 환경에 의존하지 않기 때문에, 
    - 개발 환경에서 작성한 Dockerfile을 사용하여 클라우드, 온프레미스 서버, 또는 다른 개발자의 컴퓨터에서도 동일한 애플리케이션을 실행할 수 있습니다.

1. 확장 및 유지보수 용이
    - Dockerfile은 매우 모듈화된 방식으로 이미지를 빌드할 수 있도록 해줍니다. 
    - 예를 들어, 다중 스테이지 빌드를 사용하면 하나의 Dockerfile에서 여러 단계에 걸쳐 이미지를 생성하고 최적화할 수 있습니다. 
    - 이렇게 하면 이미지의 크기를 줄이고, 보안을 강화하며, 빌드 속도를 개선할 수 있습니다.
    - 또한, Dockerfile의 각 명령어는 명확한 역할을 가지며, 쉽게 수정하고 유지보수할 수 있습니다. 
    - 새로운 기능을 추가하거나 환경 설정을 변경해야 할 때, Dockerfile의 관련 부분만 수정하면 됩니다.

1. 컨테이너화된 애플리케이션 배포
    - Dockerfile은 애플리케이션을 컨테이너화하여 배포하는 데 핵심적인 역할을 합니다. 
    - Docker 이미지는 Dockerfile을 기반으로 생성되며, 이 이미지는 컨테이너라는 독립적인 실행 환경에서 실행됩니다. 
    - 이 컨테이너는 호스트 시스템과 격리되어 실행되며, 필요한 경우 여러 인스턴스로 확장할 수도 있습니다. 
    - 따라서 Dockerfile은 애플리케이션의 배포 및 확장성을 용이하게 합니다.

1. 문서화와 협업 도구
    - Dockerfile은 애플리케이션의 실행 환경을 명확하게 문서화합니다. 
    - 이는 팀 간 협업을 촉진하는 중요한 도구가 됩니다. 
    - Dockerfile만 공유하면 다른 개발자도 동일한 환경을 재현할 수 있으므로, 팀 내에서 애플리케이션 개발, 테스트, 디버깅이 더 원활하게 이루어집니다.

1. CI/CD 파이프라인 통합
    - Dockerfile은 지속적 통합 및 지속적 배포(CI/CD) 파이프라인에 통합될 수 있습니다. 
    - CI/CD 파이프라인에서 Dockerfile을 사용해 자동으로 이미지를 빌드하고 테스트한 후, 배포할 수 있습니다. 
    - 이를 통해 코드를 커밋하면 즉시 새로운 이미지를 생성하고, 테스트한 다음 프로덕션에 배포하는 전체 프로세스를 자동화할 수 있습니다.

### 결론

- Dockerfile은 Docker 이미지를 빌드하고, 애플리케이션 환경을 구성하며, 배포하는 데 있어 핵심적인 역할을 수행합니다. 
- 이를 통해 일관성 있고 재현 가능한 환경을 제공하며, 개발, 테스트, 배포 과정에서의 효율성을 극대화할 수 있습니다. 
- Dockerfile은 개발자와 운영자가 동일한 환경에서 작업할 수 있도록 지원하며, 애플리케이션의 이동성과 확장성을 강화합니다.

### Dockerfile 기본 명령어

| Instruction | Description(ENG) | Description(KOR) |
| :---------: | :---------- | :---------- |
| ADD         | Add local or remote files and directories. | 로컬 또는 원격 파일과 디렉터리를 추가합니다. |
| ARG         | Use build-time variables. | 빌드 시점 변수를 사용합니다. |
| CMD         | Specify default commands. | 기본 명령을 지정합니다. |
| COPY        | Copy files and directories. | 파일과 디렉터리를 복사합니다. |
| ENTRYPOINT  | Specify default executable. | 기본 실행 파일을 지정합니다. |
| ENV         | Set environment variables. | 환경 변수를 설정합니다. |
| EXPOSE      | Describe which ports your application is listening on. | 애플리케이션이 수신 대기하는 포트를 설명합니다. |
| FROM        | Create a new build stage from a base image. | 기본 이미지를 사용해 새로운 빌드 단계를 만듭니다. |
| HEALTHCHECK | Check a container's health on startup. | 컨테이너 시작 시 상태를 점검합니다. |
| LABEL       | Add metadata to an image. | 이미지에 메타데이터를 추가합니다. |
| MAINTAINER  | Specify the author of an image. | 이미지의 작성자를 지정합니다. |
| ONBUILD     | Specify instructions for when the image is used in a build. | 이미지가 빌드에 사용될 때의 명령을 지정합니다. |
| RUN         | Execute build commands. | 빌드 명령을 실행합니다. |
| SHELL       | Set the default shell of an image. | 이미지의 기본 셸을 설정합니다. |
| STOPSIGNAL  | Specify the system call signal for exiting a container. | 컨테이너 종료를 위한 시스템 호출 신호를 지정합니다. |
| USER        | Set user and group ID. | 사용자와 그룹 ID를 설정합니다. |
| VOLUME      | Create volume mounts. | 볼륨 마운트를 생성합니다. |
| WORKDIR     | Change working directory. | 작업 디렉터리를 변경합니다. |

### Dockerfile 기본 명령어 자세한 설명과 예시

1. ADD

    - 역할: 파일이나 디렉터리를 호스트 머신에서 Docker 이미지의 파일 시스템으로 복사합니다.
    - 특징:
        - 로컬 파일이나 디렉터리 경로를 이미지의 파일 시스템으로 복사할 수 있습니다.
        - URL로부터 파일을 다운로드하고, 압축된 파일은 자동으로 압축 해제합니다.
        - **ADD와 COPY의 차이점은 ADD는 파일의 압축 해제와 URL에서의 다운로드를 지원한다는 점입니다.**

    ```Dockerfile
    ADD localfile.txt /app/
    ADD https://example.com/file.tar.gz /app/
    ```

1. ARG

    - 역할: Dockerfile에서 사용할 수 있는 빌드 타임 변수를 정의합니다.
    - 특징:
        - ARG는 Docker 빌드 시에만 사용되며, 컨테이너가 실행될 때는 접근할 수 없습니다.
        - --build-arg 옵션을 통해 빌드 시 변수를 전달할 수 있습니다.

    ```Dockerfile
    ARG VERSION=latest
    FROM ubuntu:${VERSION}
    ```

1. CMD

    - 역할: 컨테이너가 실행될 때 기본으로 실행할 명령어를 지정합니다.
    - 특징:
        - dockerfile에 여러 개의 CMD가 있을 경우, 마지막 CMD만 적용됩니다.
        - ENTRYPOINT와 함께 사용되면 CMD는 ENTRYPOINT에 전달될 인수로 사용됩니다.

    ```Dockerfile
    CMD ["executable", "param1", "param2"]
    ```

1. COPY

    - 역할: 파일이나 디렉터리를 Docker 이미지의 파일 시스템으로 복사합니다.
    - 특징:
        - COPY는 로컬 파일만 복사할 수 있으며, URL 복사나 압축 해제를 지원하지 않습니다.

    ```Dockerfile
    COPY ./localfile.txt /app/
    ```

1. ENTRYPOINT

    - 역할: 컨테이너가 실행될 때 항상 실행될 명령어를 지정합니다.
    - 특징:
        - ENTRYPOINT는 CMD와 결합되어 작동하며, 기본 실행 파일을 지정할 때 사용됩니다.
        - CMD는 인수로, ENTRYPOINT는 실제 실행 명령으로 주로 사용됩니다.

    ```Dockerfile
    ENTRYPOINT ["executable"]
    CMD ["param1", "param2"]
    ```

1. ENV

    - 역할: 컨테이너 내에서 사용할 환경 변수를 설정합니다.
    - 특징:
        - ENV로 설정된 변수는 컨테이너 실행 중에 모든 명령에 대해 사용 가능합니다.

    ```Dockerfile
    ENV NODE_ENV=production
    ```

1. EXPOSE

    - 역할: 컨테이너가 외부에 노출할 포트를 지정합니다.
    - 특징:
        - EXPOSE 명령어는 네트워크 포트를 문서화하지만, 실제 포트를 노출하지는 않습니다. -p 또는 -P 플래그를 사용하여 포트를 노출해야 합니다.

    ```Dockerfile
    EXPOSE 8080
    ```

1. FROM

    - 역할: 새로운 이미지를 빌드하기 위한 베이스 이미지를 지정합니다.
    - 특징:
        - 대부분의 Dockerfile은 FROM 명령어로 시작합니다.
        - 다중 스테이지 빌드를 지원하기 위해 하나의 Dockerfile에서 여러 FROM을 사용할 수 있습니다.
        - Dockerfile에서 사용할 베이스 이미지는 https://hub.docker.com/ 에서 검색하실 수 있습니다.

    ```Dockerfile
    FROM ubuntu:20.04
    ```

1. HEALTHCHECK

    - 역할: 컨테이너의 상태를 체크하는 명령어를 지정합니다.
    - 특징:
        - HEALTHCHECK 명령어를 통해 컨테이너의 상태를 주기적으로 점검할 수 있습니다.
        - 건강하지 않은 컨테이너를 재시작하는 데 사용할 수 있습니다.

    ```Dockerfile
    HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD curl -f http://localhost/health || exit 1
    ```

1. LABEL

    - 역할: 메타데이터를 이미지에 추가합니다.
    - 특징:
        - LABEL은 이미지에 대한 설명, 버전 정보 등을 저장하는 데 사용됩니다.
        - Key-Value 형식으로 메타데이터를 정의합니다.

    ```Dockerfile
    LABEL version="1.0"
    LABEL maintainer="you@example.com"
    ```

1. MAINTAINER (Deprecated)

    - 역할: 이미지의 관리자를 지정합니다.
    - 특징:
        - Dockerfile 작성자를 지정하는 용도로 사용되었으나, 현재는 LABEL을 사용하는 것이 권장됩니다.
        - 현재는 LABEL maintainer="you@example.com"과 같은 방식으로 대체합니다.

    ```Dockerfile
    MAINTAINER you@example.com
    ```

1. ONBUILD

    - 역할: 기본 이미지로 사용할 Dockerfile에서 후속 빌드 시 실행할 명령을 설정합니다.
    - 특징:
        - 다른 이미지를 생성할 때만 실행되며, 상속된 Dockerfile에서 특정 동작을 자동으로 트리거할 수 있습니다.

    ```Dockerfile
    ONBUILD RUN echo "This will run on the child image build"
    ```

1. RUN

    - 역할: 이미지 빌드 과정에서 명령어를 실행합니다.
    - 특징:
        - RUN 명령어는 각 실행 후에 새로운 레이어를 생성합니다.
        - 보통 패키지를 설치하거나, 파일 시스템을 설정하는 데 사용됩니다.

    ```Dockerfile
    RUN apt-get update && apt-get install -y nginx
    ```

1. SHELL

    - 역할: RUN, CMD, ENTRYPOINT 명령어의 실행에 사용할 기본 셸을 지정합니다.
    - 특징:
        - 명령을 실행할 때 사용할 셸을 변경할 수 있습니다. 기본 셸은 Linux에서는 /bin/sh입니다.

    ```Dockerfile
    SHELL ["/bin/bash", "-c"]
    ```

1. STOPSIGNAL

    - 역할: 컨테이너가 정지할 때 전송할 시스템 신호를 설정합니다.
    - 특징:
        - 기본 STOPSIGNAL은 SIGTERM입니다. 이 명령을 통해 다른 신호로 변경할 수 있습니다.

    ```Dockerfile
    STOPSIGNAL SIGKILL
    ```

1. USER

    - 역할: 컨테이너에서 실행할 사용자와 그룹을 설정합니다.
    - 특징:
        - 보안상 root 사용자가 아닌 다른 사용자로 실행할 때 유용합니다.

    ```Dockerfile
    USER nobody
    ```

1. VOLUME

    - 역할: 호스트와 컨테이너 간에 데이터를 공유할 수 있는 디렉터리를 지정합니다.
    - 특징:
        - 컨테이너를 삭제해도 VOLUME에 지정된 데이터는 유지됩니다.

    ```Dockerfile
    VOLUME /data
    ```

1. WORKDIR

    - 역할: 명령어가 실행될 작업 디렉터리를 설정합니다.
    - 특징:
        - 여러 WORKDIR 명령어가 사용될 경우, 상대 경로는 이전 WORKDIR에서 이어집니다.

    ```Dockerfile
    WORKDIR /app
    ```

## Dockerfile include

- Dockerfile을 환경별로(Dev, Test, Staging, Production, ...) 구성하게 되면 중복되는 소스가 발생하게 됩니다.
- 환경에 따라 변경될 부분만 dev/Dockerfile, test/Dockerfile, staging/Dockerfile, production/Dockerfile에 작성합니다
- 중복되는 소스는 base/Dockerfile에 작성합니다.
- 그리고 위에서 생성한 Dockerfile을 include 할 Dockerfile을(overlays/dev/Dockerfile) 생성합니다.

### 작성 예시

1. dev/Dockerfile

    ```Dockerfile
    FROM node:18-alpine

    ENV ENVIRONMENT=dev
    CMD ["/bin/sh", "-c", "export"]
    ```

1. base/Dockerfile

    ```Dockerfile
    COPY my_nodejs_project/ /app/

    RUN npm install

    EXPOSE 3000

    CMD ["npm", "run", "start"]
    ```

1. overlays/dev/Dockerfile

    ```Dockerfile
    # syntax = edrevo/dockerfile-plus

    INCLUDE+ ./dev/Dockerfile
    INCLUDE+ ./base/Dockerfile
    ```

## Docker 기본 명령어

- https://docs.docker.com/reference/cli/docker/

### Subcommands

| Command           | Description(ENG) | Description(KOR) |
| :---------------: | :--------------- | :--------------- |
| docker build      | (legacy builder) Build an image from a Dockerfile | Dockerfile로부터 이미지를 빌드합니다. |
| docker builder    | Manage builds | 빌드를 관리합니다. |
| docker buildx     | Docker Buildx | Docker Buildx를 사용합니다 (고급 빌드 기능). |
| docker checkpoint | Manage checkpoints | 체크포인트를 관리합니다. |
| docker compose    | Docker Compose | Docker Compose를 사용하여 다중 컨테이너 애플리케이션을 정의하고 실행합니다. |
| docker config     | Manage Swarm configs | Swarm 구성을 관리합니다. |
| docker container  | Manage containers | 컨테이너를 관리합니다. |
| docker context    | Manage contexts | Docker 컨텍스트(환경)를 관리합니다. |
| docker debug      | Get a shell into any container or image. An alternative to debugging with `docker exec`. | 컨테이너나 이미지에 쉘을 제공하며, docker exec를 대체하여 디버깅을 수행할 수 있습니다. |
| docker image      | Manage images | 이미지를 관리합니다. |
| docker init       | Creates Docker-related starter files for your project | 프로젝트를 위한 Docker 관련 시작 파일을 생성합니다. |
| docker inspect    | Return low-level information on Docker objects | Docker 객체에 대한 상세 정보를 반환합니다. |
| docker login      | Log in to a registry | 레지스트리에 로그인합니다. |
| docker logout     | Log out from a registry | 레지스트리에서 로그아웃합니다. |
| docker manifest   | Manage Docker image manifests and manifest lists | Docker 이미지 매니페스트와 매니페스트 리스트를 관리합니다. |
| docker network    | Manage networks | 네트워크를 관리합니다. |
| docker node       | Manage Swarm nodes | Swarm 노드를 관리합니다. |
| docker plugin     | Manage plugins | 플러그인을 관리합니다. |
| docker scout      | Command line tool for Docker Scout | Docker Scout의 명령줄 도구입니다 (이미지 스캔 및 분석). |
| docker search     | Search Docker Hub for images | Docker Hub에서 이미지를 검색합니다. |
| docker secret     | Manage Swarm secrets | Swarm 비밀을 관리합니다. |
| docker service    | Manage Swarm services | Swarm 서비스를 관리합니다. |
| docker stack      | Manage Swarm stacks | Swarm 스택을 관리합니다. |
| docker swarm      | Manage Swarm | Swarm을 관리합니다. |
| docker system     | Manage Docker | Docker 시스템을 관리합니다. |
| docker trust      | Manage trust on Docker images | Docker 이미지에 대한 신뢰를 관리합니다. |
| docker version    | Show the Docker version information | Docker 버전 정보를 표시합니다. |
| docker volume     | Manage volumes | 볼륨을 관리합니다. |

1. docker build
    - 기능: Docker 이미지를 빌드합니다. Dockerfile을 사용하여 애플리케이션의 이미지 레이어를 정의하고 생성합니다.
    - 사용법:
        ```bash
        docker build [OPTIONS] PATH | URL | -
        ```
    - 예시:
        ```bash
        docker build -t myapp:latest .
        ```
    - 현재 디렉토리에 있는 Dockerfile을 사용하여 myapp 이미지를 생성합니다.

1. docker builder
    - 기능: Docker 빌드 시스템을 관리합니다. 다양한 빌드 기능을 지원하며, 빌드 캐시와 관련된 작업을 수행합니다.
    - 사용법:
        ```bash
        docker builder [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker builder prune
        ```
    - 빌드 캐시를 정리합니다.

1. docker buildx
    - 기능: Docker의 다중 플랫폼 빌드를 지원합니다. 여러 플랫폼에 대해 이미지를 빌드할 수 있는 명령어입니다.
    - 사용법:
        ```bash
        docker buildx [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker buildx build --platform linux/amd64,linux/arm64 -t myapp:latest .
        ```
    - 다중 플랫폼에 대한 이미지를 빌드합니다.

1. docker checkpoint
    - 기능: 실행 중인 컨테이너의 체크포인트를 생성하고 관리합니다. 컨테이너의 상태를 저장하여 나중에 복구할 수 있습니다.
    - 사용법:
        ```bash
        docker checkpoint [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker checkpoint create mycontainer checkpoint1
        ```
    - mycontainer 컨테이너의 체크포인트를 생성합니다.

1. docker compose
    - 기능: 다중 컨테이너 Docker 애플리케이션을 정의하고 실행합니다. YAML 파일을 사용하여 애플리케이션의 서비스, 네트워크, 볼륨을 정의합니다.
    - 사용법:
        ```bash
        docker-compose [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker-compose up
        ```
    - docker-compose.yml 파일에 정의된 모든 서비스와 네트워크를 시작합니다.

1. docker config
    - 기능: Docker 서비스의 구성을 관리합니다. 특히 Docker Swarm 모드에서 비밀 구성 파일을 관리할 때 사용됩니다.
    - 사용법:
        ```bash
        docker config [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker config create myconfig config.json
        ```
    - myconfig라는 이름으로 구성을 생성합니다.

1. docker container
    - 기능: 컨테이너 관리 명령어의 그룹입니다. 컨테이너를 시작, 중지, 삭제, 검사하는 등의 작업을 지원합니다.
    - 사용법:
        ```bash
        docker container [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker container ls
        ```
    - 현재 실행 중인 컨테이너 목록을 표시합니다.

1. docker context
    - 기능: Docker CLI 환경을 관리합니다. 여러 Docker 환경(서버, 클러스터 등)에 대한 컨텍스트를 설정하고 전환할 수 있습니다.
    - 사용법:
        ```bash
        docker context [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker context ls
        ```
    - 현재 설정된 Docker 컨텍스트 목록을 표시합니다.

1. docker debug
    - 기능: Docker 디버깅 기능을 제공하며, 컨테이너와 관련된 문제를 진단할 수 있습니다.
    - 사용법:
        ```bash
        docker debug [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker debug inspect mycontainer
        ```

1. docker image
    - 기능: Docker 이미지를 관리합니다. 이미지 목록을 확인하고, 이미지 삭제, 태그 추가 등을 수행합니다.
    - 사용법:
        ```bash
        docker image [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker image ls
        ```
    - 로컬의 Docker 이미지 목록을 표시합니다.

1. docker init
    - 기능: Docker의 초기 설정을 수행합니다. 일반적으로 Docker의 설치나 초기화와 관련된 작업을 처리합니다.
    - 사용법:
        ```bash
        docker init [OPTIONS] COMMAND [ARGS...]
        ```

1. docker inspect
    - 기능: 컨테이너, 이미지, 볼륨 등의 상세 정보를 JSON 형식으로 출력합니다.
    - 사용법:
        ```bash
        docker inspect [OPTIONS] NAME|ID [NAME|ID...]
        ```
    - 예시:
        ```bash
        docker inspect mycontainer
        ```

1. docker login
    - 기능: Docker Hub 또는 다른 Docker 레지스트리에 로그인합니다.
    - 사용법:
        ```bash
        docker login [OPTIONS] [SERVER]
        ```
    - 예시:
        ```bash
        docker login
        ```

1. docker logout
    - 기능: Docker Hub 또는 다른 Docker 레지스트리에서 로그아웃합니다.
    - 사용법:
        ```bash
        docker logout [OPTIONS] [SERVER]
        ```
    - 예시:
        ```bash
        docker logout
        ```

1. docker manifest
    - 기능: Docker 이미지의 매니페스트를 관리합니다. 다중 플랫폼 이미지를 다룰 때 사용됩니다.
    - 사용법:
        ```bash
        docker manifest [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker manifest inspect myapp:latest
        ```

1. docker network
    - 기능: Docker 네트워크를 관리합니다. 네트워크 생성, 삭제, 목록 조회 등을 지원합니다.
    - 사용법:
        ```bash
        docker network [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker network ls
        ```
    - Docker 네트워크 목록을 표시합니다.

1. docker node
    - 기능: Docker Swarm 클러스터의 노드를 관리합니다. 노드 추가, 삭제, 상태 조회 등을 수행합니다.
    - 사용법:
        ```bash
        docker node [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker node ls
        ```
    - Swarm 클러스터의 노드 목록을 표시합니다.

1. docker plugin
    - 기능: Docker 플러그인을 관리합니다. 플러그인 설치, 삭제, 목록 조회 등을 지원합니다.
    - 사용법:
        ```bash
        docker plugin [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker plugin ls
        ```
    - 설치된 Docker 플러그인 목록을 표시합니다.

1. docker scout
    - 기능: Docker Scout는 컨테이너 이미지의 보안 및 최적화를 분석하는 도구입니다.
    - 사용법:
        ```bash
        docker scout [OPTIONS] COMMAND [ARGS...]
        ```

1. docker search
    - 기능: Docker Hub에서 이미지 검색을 수행합니다.
    - 사용법:
        ```bash
        docker search [OPTIONS] TERM
        ```
    - 예시:
        ```bash
        docker search nginx
        ```
    - nginx와 관련된 이미지를 Docker Hub에서 검색합니다.

1. docker secret
    - 기능: Docker Swarm에서 비밀 데이터를 관리합니다. 비밀 데이터의 생성, 삭제, 목록 조회 등을 지원합니다.
    - 사용법:
        ```bash
        docker secret [OPTIONS] COMMAND [ARGS...]
        ```
    예시:
        ```bash
        docker secret ls
        ```
    - Swarm에서 사용 중인 비밀 데이터 목록을 표시합니다.

1. docker service
    - 기능: Docker Swarm에서 서비스를 관리합니다. 서비스 생성, 업데이트, 삭제 등을 지원합니다.
    - 사용법:
        ```bash
        docker service [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker service ls
        ```
    - Swarm 클러스터에서 실행 중인 서비스 목록을 표시합니다.

1. docker stack
    - 기능: Docker Swarm에서 스택을 관리합니다. 스택 생성, 삭제, 업데이트 등을 지원합니다.
    - 사용법:
        ```bash
        docker stack [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker stack deploy -c docker-compose.yml mystack
        ```

1. docker swarm
    - 기능: Docker Swarm 모드를 관리합니다. 클러스터 초기화, 조인, 업데이트 등을 지원합니다.
    - 사용법:
        ```bash
        docker swarm [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker swarm init
        ```

1. docker system
    - 기능: Docker 시스템의 상태를 관리합니다. 리소스 정리, 상태 점검 등을 수행합니다.
    - 사용법:
        ```bash
        docker system [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker system df
        ```
    - Docker 시스템의 디스크 사용량을 표시합니다.

1. docker trust
    - 기능: Docker 이미지의 서명을 관리합니다. 이미지의 신뢰성을 보장하는 데 사용됩니다.
    - 사용법:
        ```bash
        docker trust [OPTIONS] COMMAND [ARGS...]
        ```

1. docker version
    - 기능: Docker 클라이언트와 서버의 버전 정보를 표시합니다.
    - 사용법:
        ```bash
        docker version [OPTIONS]
        ```
    - 예시:
        ```bash
        docker version
        ```

1. docker volume
    - 기능: Docker 볼륨을 관리합니다. 볼륨 생성, 삭제, 목록 조회 등을 지원합니다.
    - 사용법:
        ```bash
        docker volume [OPTIONS] COMMAND [ARGS...]
        ```
    - 예시:
        ```bash
        docker volume ls
        ```
    - Docker 볼륨 목록을 표시합니다.
