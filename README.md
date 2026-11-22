# 흥부작은도서관 · 22년생 추천 그림책 웹앱

울진군 통합도서관(흥부작은도서관) 실제 소장 도서 중 22년생(만 4~5세) 눈높이 그림책 추천과, 현재 대출 중인 책의 반납 일정을 보여주는 단일 HTML 웹앱입니다.

- 앱: https://totostory13.github.io/heungbu-library/
- 소스: `index.html` (단일 파일, 외부 의존 없음)

찜·대출 일정은 브라우저 localStorage에 저장됩니다.

## 배포 방식 (고칠 때 꼭 읽기)

- 서비스 중인 페이지의 소스는 **`gh-pages` 브랜치 루트**입니다(`main` 아님). `index.html`과 `.nojekyll`만 올라가 있습니다.
- 이 저장소에는 `remote.origin.push` 규칙이 걸려 있어 **`git push` 한 번으로 `main`과 `gh-pages`가 함께 갱신**되고, Pages가 자동으로 다시 빌드됩니다.
  확인: `git config --get-all remote.origin.push`
- `gh-pages`를 쓰는 이유: GitHub 연결(Pickle App)에 workflows·Pages 권한이 없어 `.github/workflows/pages.yml` 푸시와 Pages API 설정이 차단됩니다. 그래서 워크플로 대신 `gh-pages` 푸시로 Pages를 활성화했습니다. (로컬에 남아 있는 `.github/workflows/pages.yml`은 `.git/info/exclude`로 제외되어 커밋되지 않습니다.)
- 소스를 `main`으로 바꾸고 싶다면 GitHub 웹에서 저장소 → Settings → Pages → Source를 "Deploy from a branch", Branch `main` /(root)로 지정하면 됩니다.
