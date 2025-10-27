# Table 태그
- 데이터를 체계적으로 정리하여 보여줄 때
- <table>, <thead>, <tbody>, <tfoot>, <tr>, <th>, <td> 구성

사용법)
- <table>: 테이블을 시작할 때 사용
- 테이블 태그 대부분의 속성은 html5에서 지원하지 않는다.

``<table border="테두리선의 두께" bordercolor="선의색" width="넓이" heigth="높이" background="바닥이미지" bgcolor="바닥색" align="수평정렬" valign="수직정렬" cellpadding="td안여백" cellspacing="td사이여백">`` 

- <tr>: 행을 시작할 때 사용 (자식태그로 <th>, <td>만 정의할 수 있다.)

``<tr height="높이" background="바닥이미지" bgcolor="바닥색" align="수평정렬" valign="수직정렬">``

- 수평정렬: left, right, center
- 수직정렬: top, middle, bottom

- <th>: 열의 제목을 설정할 때 사용 (진하게, 가운데 정렬 수행)
- <td>: 열에 들어가는 데이터를 설정할 때 사용 (일반글자, 왼쪽 정렬)

``<td width="넓이" height="높이" background="바닥이미지" bgcolor="바닥색" align="수평정렬" valign="수직정렬" colspa="합칠칸의 수" rowspan="합칠행의 수>``

- <thead>, <tbody>, <tfoot>: 의미적인 태그

작성법
1. 테이블 시작
<table>

2. 행만들기
<tr>

3. 칸만들기
<td>값</td>,,,

4. 행 닫기
</tr>

n. 테이블 닫기
</table>

## 복잡한 모양의 테이블
- 칸 합치기: colspan="합칠칸의 수"

[!칸 합치기](images/colspan.jpg)

