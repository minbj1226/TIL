## 백업
- exp.exe 사용
- 모든계정은 백업이 가능
- 정기백업, 비정기 백업

사용법)
- 테이블만 백업) exp userid=계정명/비번 tables=백업할테이블명,,, file=저장할 경로
- 모든 객체) exp userid=계정명/비번 full=y file=저장할경로/파일명.dmp

## 복원
- imp.exe 사용
- 모든 계정은 복원 가능
- 동일한 테이블이 존재하면 복원이 되지 않는다.

사용법)
- 테이블만 복원) imp userid=계정명/비번 tables=복원할테이블명,,, file=백업파일명
- 모든 객체) imp userid=계정명/비번 full=y file=백업파일명