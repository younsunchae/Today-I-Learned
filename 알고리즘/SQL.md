### ๐ order by
์ฐ์ ์์๊ฐ ์๋ ์ด์ ์์๋๋ก ์ ๊ธฐ
<br/>

### ๐ like : ๋ถ๋ถ ์ผ์น
1. 'a%' : a๋ก ์์๋๋ ๋ชจ๋  ๊ฒ
2. 'a_%_%' : a๋ก ์์๋๊ณ  ์ต์ 3์ ์ด์
3. '_a%' : ๋๋ฒ์งธใ ์๋ฆฌ์ a๊ฐ ๋ค์ด๊ฐ๋ ๊ฒ
4. '%a%' : ์ค๊ฐ์ a์ด ๋ค์ด๊ฐ๋ ๊ฒ
5. not like : ๋ถ๋ถ ์ผ์น ํ์ง ์์ ๊ฒ
<br/>

### ๐ limit : ์ ํ
```sql
order by name limit 2
```
name ์ค๋ฅธ์ฐจ์์ผ๋ก ์ ๋ ฌํ ํ 2๊ฐ
<br/>

### ๐distinct : ์ค๋ณต ์ ๊ฑฐ
```sql
select count(distinct name)...
```
์ค๋ณต์ ๊ฑฐํ name count
<br/>

### ๐ ifnull : null๊ฐ ์ฐพ๊ธฐ
```sql
select ifnull(name, "NONE") as name
```
name ๊ฐ์ด null ์ด๋ฉด NONE, ์๋๋ฉด name ๊ฐ
<br/>

### ๐ date_format : date ์นผ๋ผ ์ง์ ํ ํ์์ผ๋ก ์ถ๋ ฅ
```sql
select data_format(data_time, '%Y-%m-%d')...
```
data_time์ Y-m-d ํ์์ผ๋ก ์ถ๋ ฅ<br/>
%s(์ด), %t(hh:mm:SS) ๋์๋ฌธ์ ๋ณ๋ก ์ถ๋ ฅ ํ์ ๋ค๋ฆ
<br/>

### ๐ group by 
```sql
 group by user_id, product_id having count(*) >=2 
 ```
 user_id์ product_id๊ฐ 2๊ฐ ์ด์์ธ ํ ์ฐพ๊ธฐ
 <br/>

 ### ๐ join

 #### inner join : ๊ต์งํฉ
 ```sql
 select test1.number from test1 join test2 on test1.number = test2.number; 
```
```sql
select distinct c.cart_id from cart_products c inner join cart_products p on(c.cart_id = p.cart_id) where (c.name ='์ฐ์ ' and p.name='์๊ฑฐํธ') or (c.name='์๊ฑฐํธ' and p.name='์ฐ์ ') order by c.cart_id;
```
<br/>

#### outer join : ๋งค์นญ๋๋ ๊ฐ์ด ์์ด๋ ์ถ๋ ฅ
```sql
select test1.*, test2.number from test1 left outer join test2 on test1.number = test2.number;
```

### ๐ union
์ค๋ณต๊ฐ ์ ๊ฑฐํ๋ฉด์ ํ์ด๋ธ ํฉ์น๊ณ  ์ถ์ ๋
```sql
select * from customers union select city from orders order by city
```


#### union all
์ค๋ณต๊ฐ ์ ์ ๊ฑฐ ํ๊ณ  ์ถ์ ๋
<br/>

### ๐ case
```sql
select seq
    case
        when (์กฐ๊ฑด) then ๊ฒฐ๊ณผ
            case 
        when(์กฐ๊ฑด) then ๊ฒฐ๊ณผ
        else ๊ฒฐ๊ณผ
        end as case_result
    from 'user' u
```
else ์๋ต ํ๋ฉด ํด๋จ