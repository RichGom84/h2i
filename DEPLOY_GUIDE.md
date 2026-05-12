# 🚀 H2I Vercel 배포 가이드 (초보자용)

> 권대표님이 5~10분 안에 배포 완료할 수 있는 단계별 가이드입니다.

---

## 📋 배포 전 준비물 체크리스트

- [x] GitHub 계정 (없으면 https://github.com 에서 가입)
- [x] Vercel 계정 (없으면 https://vercel.com 에서 GitHub로 가입 - 30초)
- [x] 이번에 생성된 배포 파일들 (`/h2i-deploy` 폴더)

---

## 🎯 배포 방식 선택

두 가지 방식 중 더 편한 쪽을 선택하시면 됩니다.

### 방식 A: **드래그앤드롭 배포** ⭐ 가장 쉬움 (3분)
GitHub 없이 Vercel에 폴더만 끌어다 놓으면 끝.

### 방식 B: **GitHub 연동 배포** (5분, 추후 수정·관리 편함)
GitHub에 코드를 올린 뒤 Vercel과 자동 연동. **장기 운영에 추천.**

---

## 🟢 방식 A: 드래그앤드롭 배포 (가장 빠름)

### Step 1. Vercel 가입·로그인
1. https://vercel.com/signup 접속
2. **Continue with GitHub** 클릭 (GitHub 계정으로 가입)
3. 약관 동의 후 가입 완료

### Step 2. 새 프로젝트 만들기
1. 로그인 후 우측 상단 **Add New** 버튼 클릭
2. **Project** 선택

### Step 3. 폴더 업로드
1. 페이지 하단의 **"Import a third-party Git repository"** 무시
2. 또는 직접 업로드 옵션이 있는 페이지 사용:
   - https://vercel.com/new 에서 우측의 **"deploy a template"** 영역 아래에
   - **"Or, deploy a Pre-built project"** 옵션 활용
3. **권장: GitHub 방식으로 진행하시는 것이 더 안정적입니다** → 아래 방식 B 참고

> ⚠️ Vercel은 2024년부터 드래그앤드롭을 점점 줄이는 방향이라 **방식 B (GitHub 연동)를 강력 추천**합니다.

---

## 🟢 방식 B: GitHub 연동 배포 ⭐ 강력 추천

### Step 1. GitHub에 저장소 만들기

1. https://github.com/new 접속
2. 다음과 같이 입력:
   - **Repository name**: `h2i-converter` (또는 원하는 이름)
   - **Description**: `HTML 카드뉴스를 이미지로 변환하는 무료 도구 by 권티처`
   - **Public** 선택 (무료 Vercel 배포에 필요)
   - **Add a README file** 체크 안함 (이미 있음)
   - **Add .gitignore** None
   - **License** MIT
3. **Create repository** 클릭

### Step 2. 파일 업로드

저장소가 만들어지면 빈 페이지가 나옵니다. **두 가지 방법** 중 선택:

#### 방법 1: 웹에서 바로 업로드 (가장 쉬움) ⭐
1. 빈 저장소 페이지에서 **"uploading an existing file"** 링크 클릭
2. `/h2i-deploy` 폴더 안의 모든 파일을 끌어다 놓기:
   - `index.html`
   - `README.md`
   - `vercel.json`
   - `.gitignore`
3. 페이지 하단 **Commit changes** 클릭

#### 방법 2: Git CLI 사용 (개발자용)
```bash
cd /path/to/h2i-deploy
git init
git add .
git commit -m "Initial commit: H2I v1.0 by 권티처"
git branch -M main
git remote add origin https://github.com/[권티처-username]/h2i-converter.git
git push -u origin main
```

### Step 3. Vercel에서 GitHub 저장소 가져오기

1. https://vercel.com/new 접속
2. **Import Git Repository** 섹션에서 방금 만든 `h2i-converter` 저장소를 찾기
3. 저장소가 보이지 않으면 **Adjust GitHub App Permissions** 클릭해서 권한 허용
4. 저장소 옆 **Import** 버튼 클릭

### Step 4. 프로젝트 설정 (대부분 자동)

다음 화면에서 설정 항목들이 나옵니다.

| 항목 | 값 |
|---|---|
| **Project Name** | `h2i-converter` (자동 입력됨, 그대로 두기) |
| **Framework Preset** | `Other` (자동 감지) |
| **Root Directory** | `./` (기본값) |
| **Build Command** | 비워두기 |
| **Output Directory** | 비워두기 |
| **Install Command** | 비워두기 |

→ **Deploy** 버튼 클릭

### Step 5. 배포 완료 (보통 30초~1분)

배포 진행률이 표시되고, 완료되면 다음과 같은 화면이 나옵니다.

- 🎉 **Congratulations!** 메시지
- 미리보기 화면 표시
- 도메인: `https://h2i-converter-XXX.vercel.app` 같은 형태

→ **Visit** 버튼 클릭하면 실제 배포된 사이트로 이동!

---

## 🎨 배포 후 추가 작업 (선택)

### 1. 프로젝트 이름 변경 (도메인 짧게)

1. Vercel 대시보드 → 프로젝트 클릭
2. **Settings** 탭 → **General** 메뉴
3. **Project Name**을 `h2i` 또는 `kwonteacher-h2i`로 변경
4. 새 도메인: `https://h2i.vercel.app` (이미 사용 중이면 자동으로 `-XX` 붙음)

### 2. SEO·소셜 공유 이미지 생성

Vercel에서 자동으로 Open Graph 이미지를 생성하려면:
- 별도 OG 이미지(`og-image.png`)를 만들어 업로드하면 카카오톡·페이스북 공유 시 미리보기에 표시됨
- 권장 사이즈: 1200 × 630
- 권티처 다크 민트 디자인으로 별도 제작 가능 (요청 시 자비스가 만들어드림)

### 3. 커스텀 도메인 연결 (선택)

도메인이 있으시면:
1. **Settings** → **Domains**
2. 도메인 입력 (예: `h2i.kwonteacher.com`)
3. DNS 설정 가이드 따라 CNAME 추가

---

## 🔄 업데이트하는 방법

배포 후 코드를 수정하고 싶을 때:

1. GitHub 저장소에서 `index.html` 클릭
2. 우측 상단 연필 아이콘 (Edit) 클릭
3. 수정 후 **Commit changes** 클릭
4. → Vercel이 **자동으로 재배포** (1분 이내)

자비스가 수정사항 만들어드리면, 권대표님은 새 파일을 GitHub에 올리시기만 하면 됩니다.

---

## 📣 배포 후 권티처 브랜딩 활용 전략

### 1. 네이버 블로그 포스트 작성
"권티처가 만든 무료 HTML→이미지 변환 도구 H2I 공개" 포스트로 GEO 전략 실행

### 2. Threads·인스타그램 홍보
직접 만든 카드뉴스를 H2I로 변환해서 게시하면서 "이 카드뉴스는 H2I로 만들었습니다" 멘트 추가

### 3. 강의 시간 활용
강의 중 "여러분도 무료로 쓰실 수 있어요" 하면서 시연
→ 수강생이 권티처 블로그로 유입되는 자연스러운 채널

### 4. GEO 키워드 선점
- "HTML 카드뉴스 만들기"
- "클로드 카드뉴스 PNG"
- "ChatGPT 카드뉴스 이미지 변환"
- "AI 카드뉴스 무료 도구"

위 키워드로 검색 시 H2I가 상위에 노출되도록 메타태그·구조화데이터(JSON-LD)를 이미 적용해두었습니다.

---

## ❓ 자주 묻는 질문 (FAQ)

### Q1. 배포 비용이 발생하나요?
**A**: 무료입니다. Vercel Hobby 플랜은 개인 프로젝트에 무제한 무료입니다.

### Q2. 트래픽이 많이 늘어나면 어떻게 되나요?
**A**: 월 100GB 대역폭까지 무료. 일반 도구 사용량으로는 수천 명이 써도 충분합니다.

### Q3. HTTPS는 자동으로 적용되나요?
**A**: 네, Vercel은 모든 배포에 자동 HTTPS를 제공합니다.

### Q4. 도메인을 바꿀 수 있나요?
**A**: 네, 프로젝트 이름 변경 또는 커스텀 도메인 연결로 자유롭게 변경 가능합니다.

### Q5. 코드를 수정하면 어떻게 반영되나요?
**A**: GitHub에 코드를 푸시하면 Vercel이 자동 감지해 재배포합니다 (1분 이내).

---

## 🆘 문제 발생 시 (트러블슈팅)

### 배포가 실패할 때
- `vercel.json` 파일이 올바르게 있는지 확인
- `index.html`이 루트에 있는지 확인 (서브폴더 X)

### 사이트가 안 열릴 때
- Vercel 대시보드 → Deployments에서 빌드 로그 확인
- 캐시 문제일 수 있으니 시크릿 창에서 다시 접속

### 도메인이 작동 안 할 때
- DNS 전파에 최대 48시간 소요
- nslookup 명령으로 DNS 확인

---

## ✅ 최종 체크리스트

배포 완료 후 다음을 확인하세요:

- [ ] 사이트가 정상적으로 열리는가
- [ ] HTML 파일 업로드가 작동하는가
- [ ] 카드 변환이 정상 동작하는가
- [ ] 개별 다운로드가 되는가
- [ ] ZIP 일괄 다운로드가 되는가
- [ ] 모바일에서도 정상 표시되는가
- [ ] 페이지 제목·메타태그가 올바르게 표시되는가
- [ ] 권티처 블로그 링크가 작동하는가

---

## 🎁 다음 단계 제안

배포가 완료되면 자비스가 도와드릴 수 있는 후속 작업들입니다:

1. **GEO 최적화 블로그 포스트** — 도구 출시 알리는 levelupai 블로그 글
2. **Threads 카드뉴스 10장 세트** — 도구 소개 + 사용 방법
3. **Open Graph 이미지** — 카카오톡·페이스북 공유 시 미리보기 이미지
4. **유튜브 쇼츠 스크립트** — 1분 시연 영상용 스크립트
5. **강의용 슬라이드** — H2I 시연 시 사용할 다크 민트 슬라이드

원하시는 것을 말씀해주시면 즉시 작업 들어가겠습니다!

---

**제작·문서: 자비스 (AI강사 권티처의 AI 어시스턴트)**  
**© 2026 휴먼AI연구소**
