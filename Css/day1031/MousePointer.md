# 마우스 포인터 변경
- cursor 속성으로 변경

사용법)
- `cursor: 값;`
	- 값: pointer, crosshair, progress, move, wait
	
## 디자인 설정
- position 속성사용(특정 대상을 원하는 위치에 배포하여 보여줄 수 있다.)

사용법)
- `position: 값;`
	- fixed: 고정좌표-스크롤바가 움직이면 설정된 좌표를 스크롤 바에 맞게 좌표 수정하는 방식(스크롤 바가 움직이면 대상 좌표가 변경되어 따라온다.)
			   -좌표를 갱신한다.
			   -fixed의 시작좌표는 relative에 영향을 받지 않는다.	
	- absoulte: 절대좌표-스크롤 바가 움직여도 설정된 좌표 값이 변하지 않는 좌표 형식(스크롤 바가 움직이더라도 대상 좌표가 변경되지 않아 대상이 따라오지 않는다.)
				 -absolute에 시작좌표는 relative에 영향을 받는다.
				 -absolute 속성을 가진 대상이 relative의 자식으로 생성된 경우만
				 
	- relative: 상대좌표-absolute에 시작좌표 지점을 변경할 때 사용

- 좌표 설정: top 또는 
