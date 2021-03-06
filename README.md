## 1. DKBMC 비즈니스 블로그 작성 방법

### 1-1. Hugo 설치
 - [Hugo 공식 GitHub](https://github.com/gohugoio/hugo/releases)에서 운영체제에 맞는 최신버전 다운로드
 - C:\Hugo\bin 디렉토리 생성 후 다운받은 압축파일 해제
 - 어느 위치에서나 Hugo가 실행될 수 있도록 `$ set PATH=%PATH%;C:\Hugo\bin` 명령으로 환경변수에 `C:\Hugo\bin` 추가
 - 명령 프롬프트에 `$ hugo version` 으로 동작 확인<br/>
 (ex - Hugo Static Site Generator v0.55.6-A5D4C82D windows/amd64 BuildDate: 2019-05-18T07:57:00Z)

### 1-2. DKBMC 기술블로그 소스 가져오기
 - C:\Hugo\blog 디렉토리 생성
 - 해당 디렉토리에 [https://github.com/DK-Business/blog-source](https://github.com/DK-Business/blog-source)에서 블로그 소스 Clone이나 다운로드

### 1-3. 게시글 작성
 - `$ hugo new post/파일이름.md` 명령을 입력하면 `\content\post\파일이름.md`에 파일 생성
 - 생성된 파일을 편집
  - `categories` : 자신의 게시글에 관한 카테고리 리스트를 자유롭게 추가 & 변경
  - `author` : 작성자 이름 입력
  - `title`  : 게시글 제목
  - `description` : 게시글의 간단한 부가 설명
  - `draft` : 값이 false일 경우 공개글, true일 경우 비공개글
  - `image` : 썸네일 이미지 URL 입력 (비워놔도 상관없지만, 이미지 URL 넣는 것을 권장드립니다.)
  - 무료 이미지 사이트 추천 !["https://unsplash.com/"]("https://unsplash.com/")
  - +++ 아래에 내용 작성 (`html코드`나 `마크다운`으로 작성 가능)

### 1-4. 게시글 Local 서버에서 확인
 - `$ hugo server -D` 명령을 입력
 - `localhost:1313`에 접속하여 자신의 게시글 확인

### 1-5. 게시글 업로드
 - `git init`
 - `git remote add origin https://github.com/DK-Business/blog-source`
 - `git pull origin master`
 - `git add .`
 - `git commit -m "커밋메세지"`
 - `git push origin master`
 - 소스 업로드 후 블로그 관리자에게 배포 요청

 ## 2. 게시글 작성 스타일 가이드 (Markdown)
 [마크다운 관련 문서](https://heropy.blog/2017/09/30/markdown/)에서 참고바랍니다.

 ---
 
 ![하이라이트](https://DK-Business.github.io/img/highlight.png)
 
 위의 이미지 처럼 코드박스를 만드려면,

 {{< highlight html >}}

   ...
   
 {{< /highlight >}}

 안에 코드를 입력하시면 됩니다.

 ## 3. 블로그 배포 (관리자 only)
  - 배포 요청이 있을 시 `https://github.com/DK-Business/blog-source` pull 받은 후
  - `$ hugo server -D` 명령을 입력
  - `localhost:1313`에 접속하여 배포될 게시글 검수
  - 검수 완료시 `$ hugo` 명령 입력하여 Build
  - `cd public` 빌드된 public 폴더로 이동 후
  - `git init`
  - `git remote add origin https://github.com/DK-Business/dk-business.github.io`
  - `git add .`
  - `git commit -m "커밋메세지"`
  - `git push origin master`
