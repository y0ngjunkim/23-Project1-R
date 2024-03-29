# 김용준 602377105
<h2>05월 25일</h2>
* 오늘 배운 내용 정리

### 방사형 차트
     다중 변수 데이터를 2차원 평면상에 시각화 할 수 있는 도구
```R
     install.packages('fmsb')
     library(fmsb)

     #데이터 준비
     score = c(80,60,95,85,40)
     max.score = rep(100,5)  #100을 5회 반복
     min.score = rep(0,5)    #0을 5회 반복
     ds = rbind(max.score,min.score, score)
     ds = data.frame(ds) #매트릭스를 데이터프레임으로
     colnames(ds) = c('국어','영어','수학','물리','음악')
     ds

     radarchart(ds)
```
### 텍스트 마이닝
     다중 변수 데이터를 2차원 평면상에 시각화 할 수 있는 도구
```R
     install.packages('wordcloud')
     library(wordcloud)

     word = c("홍길동", "강감찬", "이순신", "유관순", "을지문덕")
     frequency = c(851, 222, 431, 234, 542)

     wordcloud(word, frequency, colors = rainbow(length(word)))
```
<h2>05월 18일</h2>
* 오늘 배운 내용 정리

### 정렬
     정렬(sorting)은 주어진 기준에 따라 데이털 크기순으로 재배열하는 과정

     * 숫자의 경우 숫자의 크기에 따라 정렬 가능
     * 문자열의 경우 알파벳순 따라 가나다순으로 정렬 가능
     * sort() 함수: 값의 크기에 따라 값들을 정렬하는 함수 
     * order() 함수: 값의 크기에 따라 값들의 인덱스를 정렬하는 함수
```R
     name <- c('정대','강재','신현','길동') #name 정의
     sort(name)
     name
     sort(name, decreasing = T) #내림차순
     order(name)
     order(name, decreasing = F) #오름차순
     idx <- order(name)
     name[idx] #name 함수 값 출력
```

### 샘플링
     샘플링 주어진 값들에서 임의의 개수 만큼 값을 추출하는 작업

     * 여러번 값을 추출할 때,
     * 비복원 추출: 한번 뽑은 값을 제이한 뒤 새로운 값을 추출하는 방식
     * 복원 추출: 뽑았던 값을 다시 포함싴 새로운 값을 추출하는 방식
     * 샘플링이 필요한 떄
     * 데이터셋이 너무 커 분석에 시간이 많이 걸리는 경우 일부의 데이터만 추출하여 대략의 결과를 미리 확인
```R
     idx <- sample(1:nrow(iris), size=50, replace=F)
     iris.50 <- iris[idx,]
     dim(iris.50)
     head(iris.50)

     sample(1:20, size=7) #랜덤출력

     set.seed(100)
     sample(1:20, size=5)
```
<h2>05월 11일</h2>
* 오늘 배운 내용 정리

### 다중변수 데이터
```R
head(pressure)

plot(pressure$temperature,  # x축 데이터
     pressure$pressure,     # y축 데이터
     main = '온도와 기압',   # 그래프 제목
     xlab = '온도(화씨)',    # x축 레이블
     ylab = '기압'           # y축 레이블
     )
```
![데이터](https://github.com/y0ngjunkim/23-Project1-R/assets/79886468/c032c6b7-f2a4-4bbb-9f70-05621f701467)

### 걸측값
```R
z <- c(1,2,3,NA,5,NA,7)   # 걸측값이 포함한 백터
sum(z)                    # 정상 계산이 되지 않음
is.na(z)                  # NA 여부 확인
sum(is.na(z))             # NA의 개수 확인
sum(z, na.rm = TRUE)
```
<h2>05월 04일</h2>
* 오늘 배운 내용 정리

### 선그래프
```R
month =1:12
late1 =c(3,4,5,1,5,3,7,2,89,2,32,12)
late2 =c(3,4,3,1,5,3,7,2,8,2,12,12)
plot (month,    # x데이터
late1,          # y데이터
main = 'late student',
type='b',       # 그래프 종류 선택
lty=1,          # 선의 종류 선택
col='red',      # 선의 색상 선택
xlab='MOnth',   # x축 레이블
ylab='late cnt')# y축 레이블

lines (month,   # x 데이터, line()함수는 그래프 위에 선을 겹쳐 그리는 역할을 한다
late2,          # y데이터
type='b',       # 선의 종류 선택
col='blue')     # 선의 색상 선택
```

### 데이터
```R
# 데이터 준비
installed.packages('carData')
library(carData)
room.class <-TitanicSurvival #선실 정보
room.class

# 도수 분포 계산 tbl <-table (room.class)
tbl
sum(tbl) #전체 탑승객수

# 막대 그래프 생성
barplot(tbl, main='선실병 탑승객',
xlab='선실등급',
ylab='탑승객수',
col=c ('blue','green','yellow.))

# 원그래프 작성
tbl/sum(tbl)
par (mar=c(1,1,4,1))
pie(tbl,main ='선신별 탑승객',
col=c('blue','green','yellow'))
par(mar=c(5.1,4.1,4.1,2.1))
```
<h2>04월 27일</h2>
* 오늘 배운 내용 정리

### 막대그래프 = barplot
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
barplot(ds, main = 'Favorite Season',
        col = c('yellow','blue','red','green')) // 막대그래프 별로 색 지정
```
![barplot](https://user-images.githubusercontent.com/79886468/234840036-302e4c8e-ae8e-44f6-8a37-da4ec1d4e09c.png)

#### x축 y축 이름 지정 = xlab, ylab
```R
barplot(ds, main = 'Favorite Season',
        col = c('yellow','blue','red','green'), 
        xlab='계절', ylab='빈도수') // x축 y축 이름 지정
```
![barplot](https://user-images.githubusercontent.com/79886468/234839874-fdca6650-080e-47b8-ae5b-81ca5163bbf7.png)

#### 수평그래프 = horiz
```R
barplot(ds, main = 'Favorite Season',
        col = rainbow(4), xlab='계절', ylab='빈도수',
        horiz=TRUE) // 수평그래프
```
![barplot](https://user-images.githubusercontent.com/79886468/234839742-cf637ac0-d826-4ddb-aa89-042df675d04b.png)

#### 그래프 이름 지정 = name
```R
barplot(ds, main = 'Favorite Season',
        col = rainbow(4), 
        xlab='계절', ylab='빈도수',
        name=c('가을','봄','여름','겨울')) // 이름 지정
```

#### 수직방향 출력 = las
    0: 축방향(기본값)
    1: 수평 방향(축 방향과 상관없음)
    2: 축을 기준으로 수직 방향
    3: 수직 방향(축 방향과 상관없음)
```R
barplot(ds, main = 'Favorite Season',
        col = rainbow(4), 
        xlab='계절', ylab='빈도수',
        name=c('가을','봄','여름','겨울'),
        las='0') // 수직방향 출력
```

### 중첩 그룹의 막대그래프 = rbind
```R
age.A <- c(13709, 10974, 7979, 5050, 4250)
age.B <- c(17540, 29701, 36209, 33947, 24487)
age.C <- c(991, 2195, 5366, 12980, 19007)

ds <- rbind(age.A,age.B,age.C)
colnames(ds) <- c('1970','1990','2010','2030','2050')
ds

barplot(ds, main='인구측정',col = rainbow(3),
        beside=T, 
        legend.text = T) // 범례
```
![barplot](https://user-images.githubusercontent.com/79886468/234843453-777d4bd6-886e-4d28-8d6d-ecade5a0c23c.png)

#### 범례를 그래프 밖에 표시
```R
조건1
par(mfrow=c(1, 1), mar=c(5, 5, 5, 7)) // barplot 위에 작성
조건2
barplot(ds, main='인구측정',col = rainbow(3),
        beside=T, 
        legend.text = T, 
        args.legend = list(x='topright',bty='n',inset=c(-0.25,0)))
```
    x: 범례를 출력할 기본 위치를 지정하는데, 'topright'은 그래프 출력 영역의 위쪽에서 오른쪽을 의미
    bty: 'o'은 테두리를 표시, 'n' 테두리선을 표시X
    inset: 범례를 x축과 y축 방향을 얼마나 이동시킬지를 지정 (-1 ~ 1 사이의 값을 지정)

#### 범례의 내용 바꾸기
```R
       (생략..)
       legend.text=c('0세~14세','15세~64세','65세 이상') // 범례 내용 바꾸기
       (생략..)
```

### 히스토그램 = hist
```R
head(cars)
dist <- cars[,2] // 자동차 제어거리
dist
hist(dist,
     main = 'Histogram for 제동거리',
     xlab = '제동거리',     // x축 레이블
     ylab = '빈도수',      // y축 레이블
     border = 'blue',   // 막대 테두리색
     col = 'green',     // 막대 색
     las = 2,          // x축 글씨 방향(0~3)
     breaks = 5)        // 막대 개수 조절
```
![histogram](https://user-images.githubusercontent.com/79886468/234848836-77680505-afe5-47c9-99b7-912877d93bba.png)

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
    
