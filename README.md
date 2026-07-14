# blog_games

티스토리 블로그에 iframe으로 임베드하기 위한 웹게임 모음입니다.
각 게임은 외부 리소스/CDN 없이 `index.html` 파일 하나로 완성되어 있으며, GitHub Pages로 배포합니다.

## 폴더 구조

```
games/
  <게임이름>/
    index.html
```

## 게임 목록

| 게임 | 경로 | 설명 |
|---|---|---|
| 틱택토 대전 | [`games/tictactoe`](games/tictactoe) | 1인 AI 대전(쉬움/보통/무적) + 로컬 2인 대전 |

## GitHub Pages 배포

Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / `/(root)`

배포 후 게임 URL 형식:
```
https://euiheonjeong.github.io/blog_games/games/<게임이름>/
```

## 티스토리 삽입 방법

글쓰기 에디터를 HTML 모드로 전환 후 아래 형식으로 삽입:

```html
<iframe src="https://euiheonjeong.github.io/blog_games/games/<게임이름>/"
  width="100%" height="600" style="border:none; max-width:500px; display:block; margin:0 auto;">
</iframe>
```

## 새 게임 추가

```bash
mkdir -p games/<게임이름>
# games/<게임이름>/index.html 작성
git add games/<게임이름>/index.html
git commit -m "Add <게임이름> game"
git push
```

## 공통 제작 규칙

- 파일 하나(`index.html`)로 완성, 외부 리소스/CDN 사용 금지
- PC/모바일(세로) 반응형, 터치 이벤트 지원, 가로 400~500px 폭에서도 정상 동작
- 시작 화면·종료 화면에 광고 슬롯(`#ad-slot-top`, `#ad-slot-bottom`) 포함
- 종료 시 페이지 새로고침 없이 같은 화면에서 재시작 가능
