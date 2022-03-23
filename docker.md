- 도커 기본 저장소 보기

`docker info | grep "Docker Root Dir"`

→ 출처: https://info-lab.tistory.com/313 

---

- 컨테이너 안에 있는 파일을 로컬로 복사

“tmp-container”라는 컨테이너 내부에 “/root/data/test.md” 라는 파일이 있다고 하자.

이 파일을 로컬(호스트)의 “~/data/” 위치로 가져오려면 다음과 같이 하면 된다.

`$ docker cp tmp_container:/root/data/test.md ~/data/`

cp 명령어 뒤에 컨테이너 이름과 컨테이너 내부 데이터 경로를 “:” 로 구분해 적어준다.

그 뒤에는 데이터를 복사해올 로컬 경로를 적어주면 된다.

- 로컬의 파일을 컨테이너 안으로 복사

이번엔 로컬의 “~/data/test.md” 라는 파일을 컨테이너의 “/root/data/”로 복사해보자.

그냥 명령 인자의 순서를 반대로 해주면 된다.

`$ docker cp ~/data/test.md tmp_container:/root/data/`

→ 출처:  [https://itholic.github.io/docker-copy/](https://itholic.github.io/docker-copy/)

---

- 컨테이너 접속

`docker exec -it [컨테이너명] bash`

- 컨테이너 상태 확인

`docker ps -a`

- 컨테이너 삭제

`docker rm [컨테이너id]`

- 컨테이너 모두 삭제

`docker rm `docker ps -a -q``

- 컨테이너 이름 변경

`docker rename [변경 전 컨테이너 이름] [변경 후 컨테이너 이름]`

→ 출처 : [http://jmlim.github.io/docker/2019/02/24/docker-command/](http://jmlim.github.io/docker/2019/02/24/docker-command/)
