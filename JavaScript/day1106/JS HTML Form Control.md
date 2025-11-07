# JS에서 발생한 값을 HTML Form Control에 설정
- 값 설정(value 속성을 사용)
`<input type="text, password, hidden,,,>, <textarea>`

- name 속성
`obj.폼이름.control명.value=값;`

- id 속성
`document.getElementById("아이디").value=값;`

## 상태 변환
- checked 상태 변환
``<input type="checkbox, radio">``

``obj.폼이름.control명[인덱스].checked=true | false;``

- selected 상태 변환