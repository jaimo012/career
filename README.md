# 이재모 — AI 서비스 기획자 포트폴리오

헤드헌터·채용담당자가 30초 안에 매칭을 판단하도록 만든 **원페이지 포트폴리오 사이트**.
포지셔닝: "IT 아웃소싱 B2B 영업·사업개발로 80억 수주한 사람이 AI 서비스 기획으로 전환" — 사이트 자체가 그 주장의 증거물.

> 콘텐츠·디자인 확정값의 단일 진실원(SSOT)은 [노션 기획서](https://app.notion.com/p/376b0f1eaa548153bde8fe7ce8075d44).
> 프로젝트 운영 규칙은 [`CONTEXT.md`](./CONTEXT.md) 참조.

---

## 기술 스택

- **순수 단일 `index.html`** (HTML5 + CSS3 + Vanilla JS) — 빌드·번들러·프레임워크 없음
- **GitHub Pages** 정적 호스팅 — 비용 0원
- 외부 의존성은 폰트 CDN 2개뿐: Pretendard(본문) · JetBrains Mono(숫자·라벨)
- 인터랙션(아코디언·sticky 헤더·라이트박스)은 라이브러리 없이 순수 JS

## 디렉토리 구조

```
index.html                              사이트 전체 (HTML + CSS + JS 한 파일)
이재모_경력기술서_AI서비스기획자.pdf      상단바·푸터 다운로드 버튼 대상
images/                                 프로필·상장 이미지
images/logos/                           회사 로고 (크몽·한국산업인덱스·로지포커스)
CONTEXT.md / README.md                  문서
docs/                                   에셋 원본 (배포 제외 — .gitignore)
.claude/launch.json                     로컬 미리보기 설정 (배포 제외)
```

## 로컬 미리보기

빌드 과정이 없으므로 `index.html`을 브라우저로 바로 열면 된다.
상대경로 이미지·CDN 폰트까지 정확히 확인하려면 간단한 정적 서버 권장:

```bash
# Node가 있으면
npx -y http-server -p 4321 -c-1
# → http://localhost:4321
```

데스크탑과 **모바일 375px** 양쪽을 모두 육안 확인할 것.

## 배포 (GitHub Pages)

```bash
git add -A
git commit -m "feat: update portfolio"
git push origin HEAD:main
```

- **최초 1회**: GitHub 레포 `Settings > Pages > Source = main 브랜치 / (root)` 지정
  → `https://jaimo012.github.io/career` 발행 (반영 1~2분)
- **이후 갱신**: `git push` 하면 자동 반영
- 커스텀 도메인은 추후 `CNAME` 파일로 연결

### 배포 전 체크
- [ ] 파일명 정확히 `index.html`(소문자), 루트 위치
- [ ] 이미지 상대경로 정상(`images/...`), 깨진 이미지 없음
- [ ] PDF 파일 루트 포함 + 버튼 링크 경로 일치
- [ ] 성과 숫자·연도·회사명이 노션 기획서와 일치
- [ ] 외부 링크 전부 `target="_blank" rel="noopener"`

---

GitHub: [github.com/jaimo012](https://github.com/jaimo012)
