# 김용준 602377105
<h2>03월 22일</h2>
>오늘 배운 내용 정리

### library(ggplot2)
   * ggplot(data = iris, aes(x = Petal.Length, y = Petal.width)) + goem_

### cowsay
library(cowsay)

   * say("Hello World", by="cat")
   * say("Hello World", by="snow")

### 도움말
   * ?sort

### 변수명 작명 규칙
   * 첫글자는 영문자나 마침표로 시작하는데 일반적으로 영문자로 시작
   * 두번째 글자부터는 영문자, 숫자, 밑줄을 사용가능
   * 변수명에서 대소문자는 별개의 문자 취급
   * 변수명 중간에 빈칸을 넣을수 없음

<h2>03월 16일</h2>
>오늘 배운 내용 정리

### R언어의 특징
    * 데이터 분석에 특화되어 있음
    * 탄탄한 사용자 커뮤니티를 보유
    * 다양한 패키지를 제공
    * 미적이고 기능적인 통계 그래프를 제공
    * 편리한 프로그래밍 환경
    
#### R 프로그래밍 설치
    * R 스튜디오 공식사이트: https://www.rstudio.com/products/rstudio/download/

#### R 설치
    * R 설치 파일 사이트: https://www.r-project.org/
<h2>03월 09일</h2>
>오늘 배운 내용 정리

### Git 사용자 설정
    * Global 사용자 정보 설정: 시스템 전체에서 사용
    * 스페이스가 없으면 “ ”(double quotes)은 사용하지 않아도 됨
#### 본인 계정 등록
    $ git config --global user.name “admin”
    $ git config --global user.email “admin@naver.com”
    
#### 설정 내용 확인
    $ git config user.name
    $ admin
    $ git config user.email
    $ admin@example.com
    
