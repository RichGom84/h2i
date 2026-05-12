# H2I · HTML to Image Converter

> HTML 카드뉴스를 인스타그램 규격 이미지로 자동 변환하는 무료 웹 도구

![License](https://img.shields.io/badge/license-MIT-A8FF60)
![Version](https://img.shields.io/badge/version-1.0-A8FF60)
![Author](https://img.shields.io/badge/author-권티처-A8FF60)

## 🎯 소개

**H2I**(HTML to Image)는 클로드·챗GPT·제미나이로 만든 HTML 카드뉴스를 클릭 한 번에 1080×1350 PNG로 변환해주는 도구입니다. 휴먼AI연구소 권티처(권혁용 강사)가 AI 강의 수강생을 위해 만든 무료 도구로, 광고 없이 평생 무료로 사용할 수 있습니다.

## ✨ 핵심 기능

- ⚡ **설치 없이 즉시 사용** — 브라우저만 있으면 바로 변환
- 🔒 **100% 로컬 처리** — HTML이 서버로 전송되지 않음
- 📐 **사이즈 완전 자유** — 인스타·스토리·슬라이드·블로그 썸네일 모두 대응
- 🎨 **원본 디자인 보존** — Pretendard 폰트, CSS 스타일 그대로 유지
- 📦 **ZIP 일괄 다운로드** — 10장이든 30장이든 한 번에

## 🚀 사용 방법

1. HTML 파일을 드래그앤드롭 또는 선택
2. `.card` 클래스를 가진 섹션을 자동 감지
3. 사이즈 프리셋 선택 또는 직접 입력
4. **🎨 모두 변환하기** 클릭
5. 개별 다운로드 또는 ZIP 일괄 다운로드

## 📐 지원 사이즈 프리셋

| 용도 | 사이즈 |
|---|---|
| 인스타 4:5 | 1080 × 1350 |
| 인스타 정사각 | 1080 × 1080 |
| 스토리·릴스 | 1080 × 1920 |
| 슬라이드 16:9 | 1920 × 1080 |
| 블로그 썸네일 | 1200 × 630 |

## 🏗️ 기술 스택

- HTML5 + Vanilla JavaScript (의존성 최소화)
- `html2canvas` — HTML을 Canvas로 변환
- `JSZip` — ZIP 일괄 다운로드
- `FileSaver.js` — 파일 저장
- Pretendard 폰트

## 📂 카드 HTML 구조 요구사항

각 카드는 `.card` 클래스를 가진 섹션이어야 합니다.

```html
<section class="card card-1">
  <!-- 카드 1 내용 -->
</section>
<section class="card card-2">
  <!-- 카드 2 내용 -->
</section>
```

## 🌐 배포

이 도구는 정적 HTML 파일 하나로 동작합니다. Vercel·GitHub Pages·Netlify·Cloudflare Pages 어디에든 배포 가능합니다.

### Vercel 배포 (추천)
```bash
# Vercel CLI로 배포
npm i -g vercel
vercel --prod
```

또는 Vercel 웹사이트에서 GitHub 저장소를 연결하면 자동 배포됩니다.

## 👨‍🏫 제작자

**권혁용 강사 (권티처)**
- AI강사 · 휴먼AI연구소 대표
- 한국 GEO(Generative Engine Optimization) 분야 선구자
- 한국AI리터러시강사협회 사무총장
- 📖 [네이버 블로그](https://blog.naver.com/levelupai)

## 📜 라이선스

MIT License — 자유롭게 사용하시되 출처 표기는 환영합니다.

## 💬 문의 및 강의

AI 콘텐츠 제작, GEO, AI 리터러시 강의 문의는 권티처 네이버 블로그를 통해 연락주세요.

---

© 2026 권티처 · 휴먼AI연구소
