# Choose
- 연관된 여러 조건을 비교할 때 사용

문법)

```
<choose>
	<when test="조건식">
	조건에 맞을 때 수행될 문장들,,,
	</when>
	<when test="조건식">
	조건에 맞을 때 수행될 문장들,,,
	</when>
	
	<otherwise>
	모든 조건에 맞지 않을 때 수행될 문장들
	</otherwise>
</choose>
```

# Foreach
- 값을 반복시켜 쿼리문을 만들 때
- 값은 java.util.List나 배열로 들어가고 Map을 통해서 MyBatis로 전달

문법)

```
<foreach open="시작기호" itme="변수명" separator="구분자" close="닫힘기호" collection="map키">

</foreach>
```

동작)
open 속성이 한번만 출력되고, item 속성과 separator 속성이 반복 출력되고 close 속성이 가장 마지막으로 한번만 출력된다.

사용법)

```
Map<Stirng, Object> map=new HashMap<String, Object>();
map.put("map키", request.getParameterValues("이름"));
```

# Set
- update시에 사용
- 동적으로 set이 설정된다.

문법)

```
<update id="" parameterType="DTO">
update 테이블명
<set>

컬럼명=#{이름}, 컬럼명=#{이름},
<if test="조건식">
컬럼명=#{이름},
</if>
<if test="조건식">
컬럼명=#{이름},
</if>
</set>
where 조건컬럼명=#{getter method}
</update>
```

# Transaction 처리
- DAO method 안에서 