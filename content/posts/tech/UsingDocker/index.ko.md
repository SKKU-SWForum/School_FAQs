---
title: "Docker 사용하기"
date: 2022-07-24T13:05:30+09:00
draft: false
hero: images/commands-hero.png
menu:
  sidebar:
    name: Docker 사용하기
    identifier: tech-docker
    parent: tech
    weight: 10
---

### Contributor: 김성보 동문님        
## JAVA 환경설정

### 1. JDK 설치

```bash
$ sudo apt-get update
$ sudo apt-get install openjdk-8-jdk
```



### 2. JDK 버전 확인

```bash
$ java -version
```



### 3. JAVA_HOME 설정

```bash
$ readlink -f $(which java)
/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java
```

위 명령어를 통해 출력되는 결과는 다양할 수 있다. 이때, 해당 출력 결과의 끝에서 `/bin/java`를 제외한 경로를 `[경로]` 라고 하자.



### 4. JAVA_HOME [경로] 등록

```bash
$ sudo vi /etc/profile
```

위 명령어를 통해 켜진 편집기에서 맨 마지막 줄에 아래 코드를 입력한다.

```
export JAVA_HOME=[경로]
export PATH=$PATH:$JAVA_HOME/bin

(예시)
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
export PATH=$PATH:$JAVA_HOME/bin
```



### 5. JAVA_HOME 적용

```bash
$ source /etc/profile
```



---



## Docker 환경설정



### 1. HTTP 패키지 설치

```bash
$ sudo apt-get update
	 
$ sudo apt-get -y install \
	   apt-transport-https \
	   ca-certificates \
	   curl \
	   gnupg \
	   lsb-release
```



### 2. GPG 키 및 저장소 추가

```bash
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```



### 3. stable repository 등록

```bash
$ echo \
	  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
	  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```



### 3. Docker 엔진 설치

```bash
$ sudo apt-get update

$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```



### 4. Docker 버전 확인 및 Docker 엔진 설치 확인

```bash
$ docker --version
$ sudo docker run --rm hello-world
```



### 5. Docker-Compose 설치

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```



### 6. Docker-Compose 실행 권한 부여

```bash
$ sudo chmod +x /usr/local/bin/docker-compose
```



### 7. Docker-Compose 버전 확인

```bash
$ sudo docker-compose --version
```



### 8. sudo 없이 docker 명령어 실행하도록 설정

```bash
$ echo $USER
[사용자명]
$ sudo usermod -aG docker [사용자명]
```



---



## Spring Boot Docker Build하기



### 1. Jar 파일 생성

intellij 우측 `Gradle` -> `Tasks` -> `build` -> `bootJar` 더블클릭

![image](https://user-images.githubusercontent.com/53200166/160777205-0eed3dc3-1d3a-4647-be07-e00dbce55370.png)



그러면 `프로젝트 경로` -> `build` -> `libs` 디렉터리 안에 jar 파일이 생성되어 있음

![image](https://user-images.githubusercontent.com/53200166/160777439-f9e81720-b7cc-4c8f-9977-e8c2b7c8fe29.png)



### 2. Dockerfile 만들기

![image](https://user-images.githubusercontent.com/53200166/160777701-73d9f0c9-cd17-4bf8-b8c6-ced4b34597af.png)

jar 파일이 생성된 경로에 Dockerfile을 생성하고 아래와 같이 입력

```
FROM openjdk:8
ARG JAR_FILE=*.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]
```

- **FROM** : Docker Base Image (기반이 되는 이미지, <이미지 이름>:<태그> 형식으로 설정, java8로 코드를 작성했다면 11대신 8로 넣어줘야 합니다.)
- **ARG** : 컨테이너 내에서 사용할 수 있는 변수를 지정할 수 있다.
- **COPY** : 위에 선언했던 JAR_FILE 변수를 컨테이너의 app.jar로 복사한다.
- **ENTRYPOINT** : 컨테이너가 시작되었을 때 스크립트 실행



### 3. Docker Image 생성

jar 파일 및 Dockerfile이 존재하는 경로로 이동해서 아래 명령어를 입력한다.

끝에 `.`를 넣는 이유는, Dockerfile의 경로를 지정하기 위해서이다.

- 그냥 빌드할 때

    ```bash
    $ docker build [imageName] .
    ```

- 태그 옵션을 줘서 빌드할 때

    ```bash
    $ docker build -t [imageName]:[Tag] .
    ```

- 이미지 생성 확인

    ```bash
    $ docker image ls
    ```

※ 앞으로 `imageName`과 `repositoryName`은 동일한 명칭으로 간주함



### 4. Docker Network 생성

Docker Image에 IP를 직접 할당하기 위한 작업

Docker는 기본 네트워크 대역을 `172.17.xxx.xxx`로 사용하기 때문에, 별도의 네트워크 생성 작업을 수행하지 않으면 `172.17.0.1`부터 자동적으로 배정된다.

- Docker Network 생성

  ```bash
  $ docker network create --gateway 172.19.0.1 --subnet 172.19.0.0/21 networkName
  ```

- Docker Network 목록 확인

  ```bash
  $ docker network ls
  ```

- 특정 Docker network의 정보 확인

  ```bash
  $ docker network inspect networkName
  ```



### 5. Docker Image 실행

- 그냥 실행할 때

  ```bash
  $ docker run [repositoryName]
  ```

- tag가 있는 이미지를 실행할 때

    ```bash
    $ docker run [repositoryName]:[tag]
    ```

- IP를 할당하며 실행할 때

  ```bash
  $ docker run --network networkName --ip 172.19.0.101 repositoryName
  ```

- Port 번호를 할당하며 실행할 때

  - 아래와 같이 작성하면, 호스트 운영체제의 5005번 포트와 컨테이너의 3333번 포트가 맵핑된다. 즉, 호스트 운영체제의 5005번 포트로 전달된 데이터들이 컨테이너 환경의 3333번 포트로 포워딩된다.

  ```bash
  docker run -p 5005:3333 repositoryName
  ```

- 실행 중인 컨테이너 목록 확인

  ```bash
  $ docker ps
  ```

- 컨테이너 종료

  ```bash
  $ docker stop repositoryName
  ```




---



## DockerHub에 Image upload/download



### 1. 계정 생성 및 Repository 생성

**http://hub.docker.com**



### 2. Terminal에서 DockerHub Login

```bash
$ docker login -u [DockerHubID] -p [DockerHubPW]
```



### 3. 업로드하려는 이미지의 IMAGE ID 확인

```bash
$ docker images
REPOSITORY		TAG	IMAGE ID	CREATED			SIZE
repositoryName	1.0	4d4e41996d3	1 minutes ago	680MB
```



### 4. 업로드하려는 이미지를 이름이 고유하도록 DockerHub ID를 붙여서 복제

이 과정을 거치는 이유는, DockerHub 상에서 모든 Repository의 이름은 고유해야 하기 때문이다.

```bash
$ docker tag [원래 repository의 IMAGE ID] [DockerHubID]/[DockerHubRepositoryName]:[임의의 tag]
```



### 5. DockerHub의 Repository에 Image 업로드

```bash
$ docker push [DockerHubID]/[DockerHubRepositoryName]:[임의의 tag]
```



### 6. 업로드된 이미지 검색

```bash
$ docker search [DockerHubID]/[DockerHubRepositoryName]
```

※ `seongbo/superofficesequenceserver` 를 검색했더니 검색 결과가 나오지 않고, 해당 string의 일부를 잘라서 `seongbo/superofficeseqenceser` 라고 검색했더니 결과가 나타난다. 검색 string의 길이 제한이 있는 것 같다.



### 7. 이미지 다운로드

```bash
$ docker pull [DockerHubID]/[DockerHubRepositoryName]:[tagName]
```



---



## Docker 명령어 모음



### 1. Docker Image 확인/실행/삭제

- docker image 확인

  ```bash
  $ docker images
  ```

- docker image 실행

  ```bash
  $ docker run -i -t -d -p [hostPort]:[containerPort] --name [containerName] --hostname [containerHostName] [ImageName]:[Tag]
  ```

- docker image 삭제

```bash
$ docker rmi [ImageID]
```

- docker image 삭제 및 실행 중인 컨테이너도 강제 삭제

  ```bash
  $ docker rmi -f [ImageID]
  ```




### 2. Docker Container 확인

- 실행 중인 컨테이너만 확인

  ```bash
  $ docker ps
  ```

- 실행 중이지 않은 컨테이너까지 모두 확인

  ```bash
  $ docker ps -a
  ```



### 3. Docker Container 실행/종료/삭제

```bash
$ docker start [ContainerID]
$ docker stop [ContainerID]
$ docker rm [ContainerID]
```



### 4. Docker Container 안으로 접속

```bash
$ docker exec -it [ContainerID] /bin/bash
```



### 5. Docker Container 내부에서 작업 후 상태 저장

- 새 이미지로 저장

  ```bash
  $ docker commit -p [ContainerID] [ImageName]:[Tag]
  ```
  
- 백업 및 복원

  ```bash
  $ docker save -o [fileName].tar [ImageName]:[Tag]
  ```

  ```bash
  $ docker load < [fileName].tar
  ```

  

