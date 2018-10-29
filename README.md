#### 이미지

```
> docker images							# 설치된 이미지 목록 조회
> docker rmi <이미지이름|이미지아이디>:<태그>	# 이미지 삭제

```

#### 컨테이너

```
> docker ps								# 실행중인 컨테이너 조회
> docker ps -a							# 전체 컨테이너 조회
> docker ps -q							# 컨테이너 ID만 조회
> docker start <컨테이너이름|컨테이너아이디>		# 컨테이너 시작
> docker stop <컨테이너이름|컨테이너아이디>		# 컨테이너 정지
> docker rm <컨테이너이름|컨테이너아이디>		# 컨테이너 삭제
> docker exec <컨테이너이름|컨테이너아이디> <명령> <매개변수>	# 외부에서 컨테이너 내부 명령실행
```

#### 컨테이너 실행

```
> docker run <옵션> <이미지이름> <실행할파일>
```

* -i : 컨테이너와 상호작용
* -t : pseudo-tty(터미널)을 사용 
* -d : -i 옵션의 반대. 컨테이너를 백그라운드 실행 
* -p [외부포트]:[내부포트] : 포트포워딩 설정 ex) -p 80:8080 -> 외부에서 들어온 80포트 요청을 컨테이너의 8080 포트로 포워딩시킨다. 포트를 여러개 열고 싶으면 -p 80:8080 -p 8088:8088 -p 27017:27017 이런식으로 이어서 쓰면 된다. 
* -v : [외부절대경로]:[내부절대경로] : 컨테이너 외부(호스트) 볼륨과 컨테이너 내부 볼륨을 바인딩시킨다. 
* -c : cpu 스케줄링 점유율 (기본값 1024)
* -m : 메모리 한계 설정 
* -rm : 컨테이너가 종료되면 삭제 
* /bin/bash: 리눅스의 경우 컨테이너에서 bash 쉘을 이용



#### 허브

```
> docker search 이미지이름				# docker hub에서 이미지 검색
> docker pull <이미지이름>:<태그>			# 이미지 다운로드
```

