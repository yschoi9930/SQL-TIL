# SQL-TIL
SQL 공부는 작년부터 꾸준히하고 있는데 기록하고 있지 않은 점이 아쉬웠다.

아무래도 DB연결을 직접하기도 애매하고,, 그래서 HackerRank나 프로그래머스, SQL live를 사용해 코드 연습을 하기 때문!

그래도 흔적을 남기고자 깃헙에 TIL 형태로 기록해볼 예정

P.S 오라클이랑 Mysql이랑 계속 혼용해서 사용하는데,, 정해야 될 것 같다
<br/>
<br/>
<br/>
## 프로그래머스 SQL 고득점 kit
> 공부기간 : 22.06 

SQLD 자격증 따고 실제로 코드 짜보려고 연습을 했었다.

당시 고득점 kit에 있는 문제는 다 풀었던 것 같은데,, 지금 들어가보니 문제가 추가된 듯 보이네

나머지도 풀어보도록!
<br/>
<br/>
## 초보자를 위한 SQL 200제
> 공부기간 : 23.01 ~ 23.02

방학동안 쭉 훑었던 초보자를 위한 SQL 200제

200제를 모두 다 보진 못했고, Part1,2,3까지 연습 완료

기초 문법은 모두 구현해본 것 같다.
<br/>
<br/>
## HakerRank
> 공부 기간 : 23.03 ~

프로그래머스 문제를 다 푼 줄 알고 시작했던 해커랭크

회사 컴퓨터가 문제인지,, 자주 튕기고 조금 불편함

문제는 많은 만큼 계속해보려고 하는데 그냥 데이터 분석을 위한 SQL 레시피로 갈아탈까 생각중..
<br/>
<br/>


------------------------------------------------------
<br/>
<br/>

### 23.03.23
> 프로그래머스 문제 풀이
```
# 3월에 태어난 여성 회원 목록 출력하기
SELECT MEMBER_ID, MEMBER_NAME, GENDER, DATE_FORMAT(DATE_OF_BIRTH,'%Y-%m-%d')
FROM MEMBER_PROFILE
WHERE MONTH(DATE_OF_BIRTH) = "3" AND TLNO IS NOT NULL AND GENDER = 'w'
ORDER BY MEMBER_ID;
```
날짜 형식에 대한 문제, 자주 나오는데 자주 헷갈린다.

Oracle로는 TO_CHAR
Mysql 은 DATE_FORMAT
<br/>
<br/>

```
# 서울에 위치한 식당 목록 출력하기
SELECT I.REST_ID, I.REST_NAME, I.FOOD_TYPE, I.FAVORITES, I.ADDRESS, ROUND(AVG(R.REVIEW_SCORE), 2) AS SCORE 
FROM REST_INFO I
JOIN REST_REVIEW R
ON R.REST_ID = I.REST_ID
WHERE I.ADDRESS LIKE "서울%"
GROUP BY I.REST_ID 
ORDER BY SCORE DESC, FAVORITES DESC
```
작년에 풀 땐 프로그래머스 문제 쉬웠는데;; 꽤 복잡해졌네

(레벨1인 줄 알았는데 다시보니 레벨 4였다)

MySQL 기준 jOIN 언어 inner join, left join, right join, full outer join

Oracle 기준 inner join, left outer join, right outer join, full outer join

Join에 신경쓰느라 놓친 점이 AVG 함수를 사용했기 때문에 Group by가 필수였다.

계속 한 줄만 나와서 뭔가 했네
<br/>
<br/>

```
SELECT COUNT(USER_ID)
FROM USER_INFO
WHERE YEAR(JOINED) = '2021'  AND AGE BETWEEN 20 AND 29
```

다시 레벨1로 찬찬히...

외우자 BETWEEN 시작 AND 끝




