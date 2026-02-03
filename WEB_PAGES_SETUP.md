GitHub Pages — 빠른 배포 안내

목적
- `web/` 디렉토리에 있는 정적 파일들을 자동으로 `gh-pages` 브랜치로 배포하여 GitHub Pages로 호스팅합니다.

작동 방식
1. `main` 브랜치에 push(또는 PR 병합)가 발생하면 `.github/workflows/deploy-gh-pages.yml`가 실행됩니다.
2. 액션은 `web/` 디렉토리를 읽어 `gh-pages` 브랜치로 배포합니다.
3. 배포 후 Pages URL은 `https://<your-github-username>.github.io/<repo>/` 가 됩니다(설정이 적용되는데 시간이 걸릴 수 있음).

설정 후 확인할 것
- Actions 탭에서 배포 워크플로우가 성공적으로 실행되는지 확인하세요.
- Settings → Pages에서 Source가 `gh-pages`로 설정되어 있고, URL이 활성화되었는지 확인하세요.

추가 작업(수동)
- 필요하면 Settings → Pages에서 Custom domain을 설정(지금은 없음) 및 HTTPS 강제 적용.

참고
- 배포 디렉토리: `./web`
- GitHub Action 사용 시 `GITHUB_TOKEN`만으로 충분하며, 별도 비밀 설정은 필요 없습니다.
- 로컬에서 테스트하려면 `cd web && python3 -m http.server 8000` 등을 사용하세요.
