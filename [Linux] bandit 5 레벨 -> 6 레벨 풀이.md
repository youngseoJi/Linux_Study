## bandit 5 레벨 -> 6 레벨
> 다음 레벨의 암호는 inhere 디렉토리 아래의 파일에 저장되며 다음 속성을 모두 갖습니다. 
1. 사람이 읽을 수 있는 
2. 1033바이트 크기
3. 실행할 수 없음

>Commands you may need to solve this level
ls , cd , cat , file , du , find

-> 디렉토리계층이 급 깊어지고 파일양이 많아서 특별한 명령어를 사용해야한다는 것을 깨닫고 찾기시작안 사용했던  du, find 확인

---

## 풀이 - find

>1. 사람이 읽을 수 있는 파일 : text파일(아스키파일)인파일 찾기
2.  1033바이트 크기 : 파일 속성을 보며 용량크기 체크
3. 실행할 수 없음 : 접근권한 실랭권한인 x(execute)가 없는 파일을 찾기

- longin as : bandit5
- password : 전 4 레벨에서 복사한 비밀번호 사용 - lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

1. ls -> cd inhere  -> ls -al
해당 디렉토리의 목록조회
폴더가 왜이리 많지...? 
![](https://velog.velcdn.com/images/estell/post/0df7dcf7-56f9-4266-b169-ee75850364cf/image.png)

3. cd maybehere00 -> ls
수많은 디렉토리중 한개 선택하여 접근하여 디렉토리안 목록조회하자 엄청 많다. 
![](https://velog.velcdn.com/images/estell/post/d4433222-66db-4330-a22b-6a2bd25e4d51/image.png)

> -  모든 폴더 파일을 한개씩 조회할 순 없어서 거를 것 부터 걸러야된다.

5. cd.. 
inhere 디렉토리로 이동

### 키포인트 find 명령어 사용하기
4. find . -size 1033c
find -size 옵션 명령어로 현재 폴더에서 1033바이트 용량의 파일 찾았다. 
- find : 디렉토리 계층구조에서 파일 찾기
- -size : 파일 용량
- . : 현재 폴더 위치
![](https://velog.velcdn.com/images/estell/post/5bc0ea67-c628-4662-ab3d-03112e8646e0/image.png)

 
5. file maybehere07/.file2
해당 파일정보 확인, 아스키 파일임을 확인했다.
![](https://velog.velcdn.com/images/estell/post/7174bce1-fe8b-47ad-b335-e2f0fbb3d935/image.png)

6. .file2 접근권한 확인 - x 실행권한이 없음을 확인헀다.
>-rw-r-----  1 root bandit5 1033 Jan 11 19:19 .file2![](https://velog.velcdn.com/images/estell/post/a2da3a72-566a-4893-9572-d88ceee7ce3b/image.png)


7. cat .file2
1033 바이트 크기의 아스키 파일, text파일이며 실행 접근권한이 없는 .file2 파일 출력
- P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
![](https://velog.velcdn.com/images/estell/post/3e69cb1f-872c-4d50-836b-d2b5e45464b1/image.png)


---

## 추천 검색어 / 사이트
- 파일 크기 검색
- find 디렉토리 내 검색
- find 파일 용량으로 파일 검색 등등
>
참고한 사이트 https://coding-factory.tistory.com/804
