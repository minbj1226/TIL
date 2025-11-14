# Effect
- 효과를 설정할 때 사용

- 특정 대상을 숨기기
``$("selector").hide()``
- 특정 대상을 보이기
``$("selector").show()``
- 숨김, 보임 상태 반전
``$("selector").toggle()``

- 서서히 보이기
``$("selector").fadein(ms)``
``$("selector").fadein(ms.function(){보임이 완료 되었을 때 사용자에게 제공할 코드})``
- 서서히 숨기기
``$("selector").fadeOut(ms)``
``$("selector").fadeOut(ms.function(){숨김이 완료 되었을 때 사용자에게 제공할 코드})``
- 서서히 숨기고 보이기의 반전
``$("selector").fadeToggle(ms)``
``$("selector").fadeToggle(ms.function(){반전이 완료 되었을 때 사용자에게 제공할 코드})``

- 말아올리기
