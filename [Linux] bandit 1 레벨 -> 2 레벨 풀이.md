## bandit 2 레벨 -> 3 레벨
다음 레벨의 암호 는 홈 디렉토리에 있는 - 라는 파일에 저장됩니다.


## 풀이 

- longin as : bandit1
- password : 전 1 레벨에서 복사한 비밀번호 사용 - NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

1. ls -al  
권한정보가 -로 시작하기에 파일임을 확인
2. cat < -
< 특수인수를 사용하여 - 파일명을 출력할수 있었다.

> 다시(-) 는 리눅스에서 명령어의 옵션을 사용할때 쓰기 때문에, -가 앞에오는 파일/디렉토리를 사용, 생성, 삭제 등 명령어를 다룰려면 특수 인수를 붙여줘야한다.


![](https://velog.velcdn.com/images/estell/post/8ad2650d-cd5e-468d-bf5c-c61e05eea4c3/image.png)



### < / -- : 특수인수

- < : 파일 읽기 
 
> cat < -파일명

- -- : 파일 생성, 삭제, 나열하기

> touch -- -파일명  / rm -rf -- -파일명 
    



## 추천 검색어 / 사이트
"dashed filename"에 대한 Google 검색 -> 
[설명잘되어있는 곳](https://www.webservertalk.com/dashed-filename)
