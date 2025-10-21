# function: 반환형이 존재, 가장 마지막 줄에서는 반드시 main 기술
- 쿼리문에 넣어서 실행하는 간접실행을 한다. (직접실행은 할 수 없다.)
- 함수 확인: user_procedures DD
- 함수 삭제: drop function 함수명

문법)
```
create or replace function 함수명(변수명 데이터형,,,)
return 반환명
is
	변수 선언, recode 선언, table 선언
begin
	--쿼리문을 사용하지 않는 업무처리를 정의(시퀀스는 사용)
	
return 반환값;
end;
/
```

2. 저장) 파일명.sql

3. 간접실행
```
select 함수명(컬럼명),,,

insert into 테이블명(컬럼명,,,) values (값,,함수명(값),,)
```

# 제어문
- if, loop, for, while이 제공

if문)

단일 if)
문법)
```
if 조건식 then
	조건에 맞을 때 수행할 문장들,,,
end if;
```

if~else)
문법)
```
if 조건식 then
	조건에 맞을 때 수행할 문장들,,,
else
	조건에 맞지 않을 때 수행할 문장들,,,
end if;
```

다중 if)
문법)
```
if 조건식 then
	조건에 맞을 때 수행할 문장들,,,
elsif 조건식 then
	조건에 맞을 때 수행할 문장들,,,
elseif 조건식 then
	조건에 맞을 때 수행할 문장들,,,