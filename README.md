# 김용준 602377105
<h2>04월 27일</h2>
* 오늘 배운 내용 정리

### barplot(막대그래프)
```R
favorite <- c('winter','summer','spring','summer','summer','fail','spring','summer','winter','fail')
favorite
table(favorite)
ds <- table(favorite)
ds
barplot(ds, main = 'Favorite Season',col = '#dd77dd') // 막대그패프 색 지정
```
![barplot](https://user-images.githubusercontent.com/79886468/234840197-d0ab1787-4b7d-4a58-b370-32e99d7ed6a0.png)

#### 막대그래프 별로 색 지정 = col
```R
barplot(ds, main = 'Favorite Season',col = c('yellow','blue','red','green')) // 막대그래프 별로 색 지정
```
![barplot](https://user-images.githubusercontent.com/79886468/234840036-302e4c8e-ae8e-44f6-8a37-da4ec1d4e09c.png)

#### x축 y축 이름 지정 = xlab, ylab
```R
barplot(ds, main = 'Favorite Season',col = c('yellow','blue','red','green'), xlab='계절', ylab='빈도수') // x축 y축 이름 지정
```
![barplot](https://user-images.githubusercontent.com/79886468/234839874-fdca6650-080e-47b8-ae5b-81ca5163bbf7.png)

#### 수평그래프 = horiz
```R
barplot(ds, main = 'Favorite Season',col = rainbow(4), xlab='계절', ylab='빈도수',horiz=TRUE) // 수평그래프
```
![barplot](https://user-images.githubusercontent.com/79886468/234839742-cf637ac0-d826-4ddb-aa89-042df675d04b.png)

#### 그래프 이름 지정 = name
```R
barplot(ds, main = 'Favorite Season',col = rainbow(4), xlab='계절', ylab='빈도수',name=c('가을','봄','여름','겨울')) // 이름 지정
```

#### 수직방향 출력 = las
    0: 축방향(기본값)
    1: 수평 방향(축 방향과 상관없음)
    2: 축을 기준으로 수직 방향
    3: 수직 방향(축 방향과 상관없음)
```R
barplot(ds, main = 'Favorite Season',col = rainbow(4), xlab='계절', ylab='빈도수',name=c('가을','봄','여름','겨울'),las='0') // 수직방향 출력
```

### 중첩 그룹의 막대그래프 = rbind
```R
age.A <- c(13709, 10974, 7979, 5050, 4250)
age.B <- c(17540, 29701, 36209, 33947, 24487)
age.C <- c(991, 2195, 5366, 12980, 19007)

ds <- rbind(age.A,age.B,age.C)
colnames(ds) <- c('1970','1990','2010','2030','2050')
ds

barplot(ds, main='인구측정',col = rainbow(3),beside=T, legend.text = T) // 범례
```
![barplot](https://user-images.githubusercontent.com/79886468/234843453-777d4bd6-886e-4d28-8d6d-ecade5a0c23c.png)

#### 범례를 그래프 밖에 표시
```R
조건1
par(mfrow=c(1, 1), mar=c(5, 5, 5, 7))
조건2
args.legend = list(x='topright',bty='n',inset=c(-0.25,0))
```

<h2>04월 13일</h2>
* 오늘 배운 내용 정리

### 조건문
```R
job.type <- 'a'
if(job.type == 'b') {
  bonus <- 200
} else {
  bonus <- 100
} 
print(bonus)
```

### 반복문
```R
 while(1 <= 100){
    sum <- sum + i
    i <- i + 1
}
print(sum)   
```

### 사용자정의 함수
```R
함수명 <- function(매개변수 목록) {
    실행할 명령문(들)
    return (함수의 실행 결과)
}
```
<h2>04월 06일</h2>
<h3>경조사로 인해 수업 참여 X</h3>
<h2>03월 30일</h2>
* 오늘 배운 내용 정리

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
   
 ### 2차원 자료의 저장
    * 1차원 자료: 단일 주제의 값들을 모아 놓은 것
    * 2차원 자료: 여러 주제로 데이터를 수집한 형태
   매트릭스와 데이터프레임의 차이점은 매트릭스에 저장되는 모든 자료의 종류가 동일한 반면 데이터프레임에는 서로 다른 종류의 데이터가 저장

<h2>03월 23일</h2>
* 오늘 배운 내용 정리

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
* 오늘 배운 내용 정리

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
* 오늘 배운 내용 정리

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
    
