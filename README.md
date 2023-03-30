# 김용준 602377105
<h2>03월 30일</h2>
>오늘 배운 내용 정리

### 명령어
    * ls()		<- 리스트 확인
    * rm()		<- 해당 리스트 삭제
    * rm(list = ls())	<- 리스트 전부 삭제
    
### R에서의 자료구조
    * 1차원: 자료, 벡터, 리스트
    * 2차원: 자료 매트릭스, 데이터프레임
    
### 범주형 자료와 수치형 자료
    * 범주형 자료: '분류'의 의미를 갖는 값들로 구성된 자료로, 보통 문자로 표현되고 산술연산을 적용
    * 수치형 자료: 값들이 크기를 가지며 산술연산이 가능
   ![범수](https://user-images.githubusercontent.com/79886468/228812014-8735fdea-9b83-4f6b-b0e6-7b0e84a45f8b.png)

<h2>03월 23일</h2>
>오늘 배운 내용 정리

### ggplot
    * library(ggplot2)
    * ggplot(data = iris, aes(x = Petal.Length, y = Petal.width)) + goem_

### cowsay
    * library(cowsay)
    * say("Hello World", by="cat")
    * say("Hello World", by="snow")
   ![cat](https://user-images.githubusercontent.com/79886468/227890593-ae80fdae-2944-4e53-a7a5-0573abbcd34c.png)
   ![snow](https://user-images.githubusercontent.com/79886468/227890682-89d8d035-877e-407e-bda5-3fda0e020b34.png)

### 도움말
    * ?sort
   ![sort](https://user-images.githubusercontent.com/79886468/227890571-e1d8877b-3da2-4745-b000-62b98d7c1aff.png)

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
    
