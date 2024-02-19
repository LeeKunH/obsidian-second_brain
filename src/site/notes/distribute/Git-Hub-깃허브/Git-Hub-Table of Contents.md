---
{"dg-publish":true,"permalink":"/distribute/git-hub/git-hub-table-of-contents/","tags":["Git-Hub-깃허브","개발도구"],"noteIcon":""}
---

### 날짜 2023-12-14 09:04

-------------------------------
# 참고/연관된 기록 =>
위에서 작성한 내용과 연관성이 있는 기록-노트를 연결.
" [[]] "
- https://git-scm.com/
- https://docs.github.com/ko/get-started/quickstart/hello-world
- https://docs.github.com/ko/get-started/quickstart/git-and-github-learning-resources
- https://docs.github.com/en/get-started/quickstart/set-up-git


-------------------------------
# <깃/깃허브>
- 깃
	로컬환경-오픈 소스 배포-버전 관리 프로그램
- 깃허브


### <코딩애플>
##### ㅡ [[2강-깃코드-스테이징-레포지토리-커밋-용어이해\|2강-깃코드-스테이징-레포지토리-커밋-용어이해]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- staging area-스테이징 - "임시 저장소 느낌"
	- repository-레포지토리
	- commit-커밋-명령코드
		- "커밋하다" = "버전생성하다" = "파일 스냅샷(snapshot) 생성" = "파일 현재 상태를 기록하다"
	- `git init` - "작업폴더 깃 시작"
	- `git add`
		- `git add 파일명1 파일명2 ~`
		- `git add .` - "현재 작업 폴더 모든 파일 스테이징"
	- `git status` - "스테이징된 파일 이력 확인"
	- `git restore --staged 파일명` - "스테이징된 파일 취소(repository 영역에 있는 파일 해당 x )"
	- `git commit -m "커밋메세지 입력"`
	- `git log --all --oneline` = `--oneline --all` - "커밋 이력 확인 가능"
	- `git log --all --oneline --graph`
		- 주의
		- 플래그 명령어 순서


----
----
-----
### ㅡ [[깃허브-포크-기능용어\|깃허브-포크-기능용어]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 깃허브-Fork 기능/용어
		- 방법
	- 깃 프로젝트 버전관리
	- fork-포크 개발용어 - "코드 복사 후 새로운/독립적인 개발"
	- 오픈소스 소프트웨어
	- Pull Request


### ㅡ [[깃허브-README파일-이미지-동영상-올리는 방법\|깃허브-README파일-이미지-동영상-올리는 방법]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 깃허브 README 파일 이미지-동영상 올리는 방법
	- ㅡㅡㅡㅡ
	- 깃허브 사이트-issues탭
		- 깃허브 서버
		- 이미지 경로 생성
		- 
	- 마크다운(markdown) 문법/양식
		- img태그
		- 
	- 동영상 파일 mp4형식
	- 이미지 파일 gif 형식
		- 변환 사이트
			- https://cloudconvert.com/mp4-to-gif


### ㅡ [[깃허브-issue탭-이미지첨부방법-이미지주소\|깃허브-issue탭-이미지첨부방법-이미지주소]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 깃허브 issue 이용 이미지 첨부
	- ㅡㅡㅡㅡ
	- README.md 마크다운 파일형식
		- 마크다운 문법 이용 > 이미지 첨부
		- 이미지 주소 필요
	- 이미지 주소 가져오는 방법
		- 1. 정석적인 방법 - "README존재하는 동일 repo에 이미지 저장/추가 > 이미지 경로 복사"
			- 깃허브 레포지토리 저장 이미지 주소 예시
		- 2. 깃허브 이슈탭 이용 - "본래 깃허브 이슈탭은 이미지를 올리기 위한 기능은 아니지만 활용"
			- 이미지 주소 생성
				- 왜? - "이슈에 이미지 올림 > 깃허브 서버에 이미지 업로드 > 이미지 고유주소/링크생성 = 깃허브 서버 사용"
			- 깃허브 이슈탭 이미지 주소 예시
	- 시연동영상 첨부 과정 기록


### ㅡ [[깃허브-토큰-암호키\|깃허브-토큰-암호키]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- 깃허브 토큰
	- github token
	- ㅡㅡㅡㅡ
	- 깃허브 레포지토리 <> 다른 프로그램 접근/상호작용 위한 암호키
		- 접근권한 부여
		- 
	- 토큰 생성 과정 =>
	- Settings 설정
		- 드롭다운 메뉴
	- Developer settings 설정
		- 사이드바
	- Personal Access Tokens 선택
	- 주의점

### ㅡ [[깃허브페이지-정적사이트호스팅\|깃허브페이지-정적사이트호스팅]]
- <span style="background:rgba(240, 200, 0, 0.2)">키워드/문장 기록 =></span>
	- GitHub-Pages=깃허브 페이지 -- 'GitHub깃허브 제공하는 정적 사이트 호스팅 서비스'
	- 웹사이트/웹페이지 무료 호스팅 가능
		- GitHub-Pages 이용 > gitub 기본 도메인 설정 = 깃허브 서버 이용 호스팅 = 인터넷 배포 
	- ㅡㅡㅡㅡ
	- 서버 측 렌더링=SSR 기능 지원 x
		- = 클라이언트 측 미리 렌더링(된) 정적 데이터(만) 호스팅 가능
		- = 정적파일/정적데이터만 서버측 > 클라이언트 단순 응답/제공 가능
			- = HTML-CSS-JS 파일 이용 > 웹사이트 호스팅
		- = 서버 측 실행(되는) 스크립트(파일) 지원x
			- 서버 측 스크립트 - PHP, Python
		- = 자동 실시간 반영 x = 직접 수정 > 배포
		- 
	- 렌더링 용어 -- '데이터를 실제 값으로 변환하고 사용자 화면에 보이도록 하는 과정'
	- 
	- 장점 =>
	- 깃허브 통합
		- 깃허브 저장된 데이터 이용 > 버전관리-배포 용이
	- jekyll 정적 사이트 생성기 호환 
		- 마크다운 파일=정적 콘텐츠 > 웹사이트로 변환=정적 html 페이지 변환 기능
		- 디자인(된) 템플릿 = 웹사이트 테마 = html파일
		- 
	- 배포순서 =>
	- 옵시디언 이용 마크다운 파일 생성
	- GitHub 레포지토리 업로드