### 🍀 order by
우선순위가 있는 열을 순서대로 적기
<br/>

### 🍀 like : 부분 일치
1. 'a%' : a로 시작되는 모든 것
2. 'a_%_%' : a로 시작되고 최소 3자 이상
3. '_a%' : 두번째ㅔ 자리에 a가 들어가는 것
4. '%a%' : 중간에 a이 들어가는 것
5. not like : 부분 일치 하지 않은 것
<br/>

### 🍀 limit : 제한
```sql
order by name limit 2
```
name 오른차순으로 정렬한 후 2개
<br/>

### 🍀distinct : 중복 제거
```sql
select count(distinct name)...
```
중복제거한 name count
<br/>

### 🍀 ifnull : null값 찾기
```sql
select ifnull(name, "NONE") as name
```
name 값이 null 이면 NONE, 아니면 name 값
<br/>

### 🍀 date_format : date 칼럼 지정한 형식으로 출력
```sql
select data_format(data_time, '%Y-%m-%d')...
```
data_time을 Y-m-d 형식으로 출력<br/>
%s(초), %t(hh:mm:SS) 대소문자 별로 출력 형식 다름
<br/>

### 🍀 group by 
```sql
 group by user_id, product_id having count(*) >=2 
 ```
 user_id와 product_id가 2개 이상인 행 찾기