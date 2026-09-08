# MOONLIGHT MARKET · 너구리

Canvas와 Web Audio로 구현한 단일 HTML 플랫폼 게임입니다.

- 플레이: https://neouguri-moonlight-market.ys-475.workers.dev
- 로컬 실행: `index.html`을 브라우저에서 엽니다.
- 조작: Enter 시작, 좌우 이동, 상하 사다리, Space 점프, P 일시정지.
- 최고 점수는 각 브라우저의 localStorage에 저장됩니다.

## Cloudflare 배포

Workers Static Assets로 HTML만 제공합니다. 서버 함수, 데이터베이스,
유료 서비스를 사용하지 않습니다. 정적 파일 요청은 무료·무제한입니다.
요금 정책: https://developers.cloudflare.com/workers/static-assets/billing-and-limitations/

Node.js와 npm이 설치된 환경에서 프로젝트 폴더를 열고 실행합니다.

```sh
npx wrangler@4.129.1 whoami
# 로그인되어 있지 않은 경우에만 실행합니다.
npx wrangler@4.129.1 login
# index.html 수정 후 재배포합니다.
npx wrangler@4.129.1 deploy
```

`wrangler.jsonc`에 배포 대상과 정적 파일 설정이 있습니다.
`.assetsignore`는 `index.html`만 업로드하도록 제한하므로 Git 정보,
문서, 배포 설정과 로컬 파일은 공개되지 않습니다.
현재는 수동 배포이며 Git 커밋만으로 사이트가 갱신되지는 않습니다.
