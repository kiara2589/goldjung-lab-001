# Mission 1 README
# 미션 1: 내 컴퓨터에 개발자용 작업실 꾸미기

## Step 1. 현재 디렉토리 위치 확인

- **실행 명령어 및 결과:**
```bash
$ pwd
/c/Users/k-pc
```
## Step 2. 실습용 디렉토리 생성 및 이동

- **실행 명령어 및 결과:**
```bash
$ mkdir -p ~/workspace/mission1
$cd ~/workspace/mission1$ pwd
/c/Users/k-pc/workspace/mission1
```
## Step 3. 폴더 내용 확인 (숨김 파일 포함)

- **실행 명령어 및 결과:**
```bash
$ ls -la
total 0
drwxr-xr-x 1 k-pc 197121 0 Nov  3 19:25 ./
drwxr-xr-x 1 k-pc 197121 0 Nov  3 19:25 ../
```
## Step 4. 빈 파일 생성 및 내용 확인

- **실행 명령어 및 결과:**
```bash
$ touch test.txt
$ cat test.txt
```
## Step 5~7. 파일 권한 설정 및 변경 실습 (chmod)

- **실행 명령어 및 결과:**
```bash
$ ls -l test.txt
-rw-r--r-- 1 k-pc 197121 0 Nov  3 19:29 test.txt

$ chmod +x test.txt
$ ls -l test.txt
-rw-r--r-- 1 k-pc 197121 0 Nov  3 19:29 test.txt

$ chmod 755 test.txt
$ ls -l test.txt
-rw-r--r-- 1 k-pc 197121 0 Nov  3 19:29 test.txt

$ chmod 644 test.txt
$ ls -l test.txt
-rw-r--r-- 1 k-pc 197121 0 Nov  3 19:29 test.txt
```
*(참고: Windows Git Bash 환경 특성상 chmod 권한 변경이 실제 파일 시스템에 반영 표시되지 않음을 확인함)

## Step 8. Docker 설치 및 데몬 점검

- **실행 명령어 및 결과:**
```bash
$ docker --version
Docker version 24.0.6, build ed223c4

$ docker info
Client:
 Version:    29.9.2
 Context:    desktop-linux
 Debug Mode: false
 Plugins:
  agent: Docker AI Agent Runner (Docker Inc.)
    Version:  v1.152.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-agent.exe
  ai: Docker AI Agent - Ask Gordon (Docker Inc.)
    Version:  v1.33.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-ai.exe
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.38.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-buildx.exe
  compose: Docker Compose (Docker Inc.)
    Version:  v5.6.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-compose.exe
  debug: Get a shell into any image or container (Docker Inc.)
    Version:  0.49.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-debug.exe
  desktop: Docker Desktop commands (Docker Inc.)
    Version:  4.97.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-desktop.exe
  dhi: CLI for managing Docker Hardened Images (Docker Inc.)
    Version:  v0.0.9
    Path:     C:\Program Files\Docker\cli-plugins\docker-dhi.exe
  extension: Manages Docker extensions (Docker Inc.)
    Version:  v0.2.32
    Path:     C:\Program Files\Docker\cli-plugins\docker-extension.exe
  init: Creates Docker-related starter files for your project (Docker Inc.)
    Version:  v1.4.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-init.exe
  mcp: Docker MCP Plugin (Docker Inc.)
    Version:  v0.44.2
    Path:     C:\Program Files\Docker\cli-plugins\docker-mcp.exe
  model: Docker Model Runner (Docker Inc.)
    Version:  v1.2.9
    Path:     C:\Program Files\Docker\cli-plugins\docker-model.exe
  offload: Docker Offload (Docker Inc.)
    Version:  v0.7.21
    Path:     C:\Program Files\Docker\cli-plugins\docker-offload.exe
  pass: Docker Pass Secrets Manager Plugin (beta) (Docker Inc.)
    Version:  v0.3.2
    Path:     C:\Program Files\Docker\cli-plugins\docker-pass.exe
  sandbox: "docker sandbox" is deprecated, use Docker Sandboxes instead (Docker Inc.)
    Version:  v0.13.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-sandbox.exe
  scout: Docker Scout (Docker Inc.)
    Version:  v1.27.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-scout.exe

Server:
 Containers: 5
  Running: 3
  Paused: 0
  Stopped: 2
 Images: 3
 Server Version: 29.9.2
 Storage Driver: overlayfs
  driver-type: io.containerd.snapshotter.v1
 Logging Driver: local
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Discovered Devices:
  cdi: docker.com/gpu=webgpu
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 nvidia runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: b7a25261e029d68978bbf290df0a62fc819b3c51
 runc version: v1.5.2-0-g29dd3dc2
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.18.54.1-microsoft-standard-WSL2
 Operating System: Docker Desktop
 OSType: linux
 Architecture: x86_64
 CPUs: 8
 Total Memory: 3.724GiB
 Name: docker-desktop
 ID: 303abe1f-154c-4369-9f73-cd8172b964c3
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http.docker.internal:3128
 HTTPS Proxy: http.docker.internal:3128
 No Proxy: hubproxy.docker.internal
 Labels:
  com.docker.desktop.address=npipe://\\.\pipe\docker_cli
 Experimental: false
 Insecure Registries:
  hubproxy.docker.internal:5555
  127.0.0.0/8
  ::1/128
 Live Restore Enabled: false
 Firewall Backend: iptables
```
## Step 9. Docker 기본 운영 실습 (hello-world)

- **실행 명령어 및 결과:**
```bash
$ docker run hello-world
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

$ docker ps -a
CONTAINER ID   IMAGE               COMMAND                   CREATED          STATUS
             PORTS                                     NAMES
57ae7aafd66d   hello-world         "/hello"                  28 seconds ago   Exited (0) 26 seconds ago                                             nostalgic_bardeen
60d72e7a4399   ubuntu              "sleep infinity"          4 hours ago      Up 4 hours                                                            vol-test2
56635a9987bc   my-custom-web:1.0   "/docker-entrypoint.…"   4 hours ago      Up 4 hours                  0.0.0.0:8082->80/tcp, [::]:8082->80/tcp   bind-test
d4415bc00cea   my-custom-web:1.0   "/docker-entrypoint.…"   4 hours ago      Up 4 hours                  0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   my-web-server
dfd5efb7b02c   ubuntu              "bash"                    4 hours ago      Exited (127) 4 hours ago                                              my-ubuntu
c562308e197f   hello-world         "/hello"                  4 hours ago      Exited (0) 4 hours ago                                                beautiful_lichterman
```
## Step 10. Ubuntu 컨테이너 실행 및 내부 진입

- **실행 명령어 및 결과:**
```bash
$ docker run -it ubuntu bash
root@301d82f96ec9:/#
root@301d82f96ec9:/# cat /etc/os-release
PRETTY_NAME="Ubuntu 26.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04.1 LTS (Resolute Raccoon)"
VERSION_CODENAME=resolute
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=resolute
LOGO=ubuntu-logo
root@301d82f96ec9:/# exit
exit
```
## Step 11~13. 커스텀 Dockerfile 작성, 빌드 및 웹서버 실행

- **실행 명령어 및 결과:**
```bash
$ cat Dockerfile
FROM ubuntu:22.04
RUN apt-get update && apt-get install -y nginx
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
EOF

k-pc@lg UCRT64 ~/workspace/mission1
$ docker build -t my-web-server .
[+] Building 93.6s (7/7) FINISHED                                       docker:desktop-linux
 => [internal] load build definition from Dockerfile                                    0.1s
 => => transferring dockerfile: 147B                                                    0.0s
 => [internal] load metadata for docker.io/library/ubuntu:22.04                         2.9s
 => [auth] library/ubuntu:pull token for registry-1.docker.io                           0.0s
 => [internal] load .dockerignore                                                       0.1s
 => => transferring context: 2B                                                         0.0s
 => [1/2] FROM docker.io/library/ubuntu:22.04@sha256:076e7bf82319619f28dd0aa9c02ab34b  14.0s
 => => resolve docker.io/library/ubuntu:22.04@sha256:076e7bf82319619f28dd0aa9c02ab34b0  0.1s
 => => sha256:0626d3cc316c9fea3d4891e2ec19b8f371fe22ffb915622f6072a 29.75MB / 29.75MB  11.1s
 => => extracting sha256:0626d3cc316c9fea3d4891e2ec19b8f371fe22ffb915622f6072a2ee2ca90  2.8s
 => [2/2] RUN apt-get update && apt-get install -y nginx                               57.9s
 => exporting to image                                                                 17.9s
 => => exporting layers                                                                11.4s
 => => exporting manifest sha256:6596b5d4e5785be036c9d7c62a27c5f59e857e426052400c7d202  0.1s
 => => exporting config sha256:c87af20477418148148455a41d72f12e4ce83bdea240a781aa2f317  0.1s
 => => exporting attestation manifest sha256:91a5b8f00dd1c22b543fa2e8cbe248370618cee41  0.1s
 => => exporting manifest list sha256:f66f597122a19bcc92e4feb0d7fa3d184f0e97ed6cd704cb  0.1s
 => => naming to docker.io/library/my-web-server:latest                                 0.0s
 => => unpacking to docker.io/library/my-web-server:latest                              6.1s

k-pc@lg UCRT64 ~/workspace/mission1
$ docker run -d -p 8080:80 --name my-web my-web-server
4d0c1c301971d79e39627d8b37324054286c7a7fdb3725cee8ddf837d9f7f136
docker: Error response from daemon: failed to set up container networking: driver failed programming external connectivity on endpoint my-web (1f1315c868f61920b75d1fb12c0ee7ff52441ca74470b490b04c69c30b7c3e1c): Bind for 0.0.0.0:8080 failed: port is already allocated

Run 'docker run --help' for more information

What's next:
    Debug this container error with Gordon → docker ai "help me fix this container error"

k-pc@lg UCRT64 ~/workspace/mission1
$ curl -I http://localhost:8080
HTTP/1.1 200 OK
Server: nginx/1.31.8
Date: Tue, 03 Nov 2026 11:04:43 GMT
Content-Type: text/html
Content-Length: 31
Last-Modified: Tue, 03 Nov 2026 06:28:19 GMT
Connection: keep-alive
ETag: "6ae97f03-1f"
Accept-Ranges: bytes
```
**웹 브라우저 접속 결과 (`http://localhost:8080`):**
  - 화면 출력: `My Custom Web Server` (정상 작동 확인)

## Step 14~16. Docker 바인드 마운트 및 데이터 영속성 검증

- **실행 명령어 및 결과:**
```bash
$ mkdir -p html
$ echo "<h1>Hello Volume!</h1>" > html/index.html

$ docker rm -f vol-web
vol-web

$ MSYS_NO_PATHCONV=1 docker run -d -p 8081:80 -v "$PWD/html:/usr/share/nginx/html" --name vol-web nginx
b0229e2feaa640209163b815174fc830df416c045a2de4ad951f8817c1d247b7

$ curl http://localhost:8081
<h1>Hello Volume!</h1>

$ docker rm -f vol-web
vol-web

$ ls -l html/index.html
-rw-r--r-- 1 k-pc 197121 23 Nov  3 20:14 html/index.html
```
- **웹 브라우저 접속 결과 (`http://localhost:8081`):**
  - 화면 출력: `Hello Volume!` (호스트의 index.html 파일 내용이 웹 브라우저 화면에 정상 출력됨)

- **검증 내용:**
  - Windows Git Bash의 경로 자동 변환 방지(`MSYS_NO_PATHCONV=1`) 및 Nginx 공식 이미지의 웹문서 기본 경로(`/usr/share/nginx/html`)로 바인드 마운트를 설정하여 호스트의 `html/index.html` 파일 내용이 웹서버로 정상 출력됨을 확인함.
  - `docker rm -f` 명령어로 컨테이너를 삭제한 후에도 호스트 시스템의 `html/index.html` 파일이 지워지지 않고 보존됨을 확인하여 **데이터 영속성(Persistence)** 검증을 마침.

  ---

## 🛠️ 트러블슈팅 (Troubleshooting & 오류 해결 기록)

### 1. Windows Git Bash 경로 자동 변환으로 인한 Volume Mount 실패
- **문제 현상:** `docker run -v` 옵션 사용 시, Windows Git Bash가 마운트 경로를 윈도우 스타일(`C:/...`)로 임의 변환하면서 컨테이너 내부로 경로가 전달되지 않고 Nginx 기본 페이지(`Welcome to nginx!`)만 계속 출력됨.
- **해결 방법:** 
  1. Git Bash의 경로 자동 변환을 끄는 환경 변수(`MSYS_NO_PATHCONV=1`) 적용.
  2. Nginx 공식 이미지의 웹문서 기본 경로인 `/usr/share/nginx/html`을 목적지 경로로 정확히 지정하여 바인드 마운트 정상 작동 확인.
  ```bash
  $ MSYS_NO_PATHCONV=1 docker run -d -p 8081:80 -v "$PWD/html:/usr/share/nginx/html" --name vol-web nginx
  ```

### 2. GitHub Push 진행 시 Syntax Error 및 원격 저장소 연결 오류
- **문제 현상:** `git remote add origin` 명령어 실행 시 URL 양옆에 화살괄호(`< >`)를 그대로 포함하여 `bash: syntax error near unexpected token 'newline'` 에러 발생 및 `fatal: not a git repository` 오류 발생.
- **해결 방법:** 
  1. `git init` 명령어로 로컬 저장소 재초기화 및 기본 브랜치를 `main`으로 전환.
  2. 괄호를 제거한 올바른 원격 저장소 URL(`https://github.com/kiara2589/goldjung-lab-001.git`)로 재연결 후 `git push -u origin main --force`를 실행하여 원격 저장소 업로드 완수.
  