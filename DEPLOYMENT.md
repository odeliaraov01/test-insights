# Deployment Guide 🚀

## Step 1: GitHub에 올리기

### Option A: GitHub 웹에서 (가장 간단)

1. github.com으로 이동
2. `+` 아이콘 → "New repository"
3. 레포 이름 입력 (예: `tech-blog`)
4. "Create repository"
5. 이 폴더의 모든 파일을 드래그 앤 드롭

### Option B: 터미널에서

```bash
git init
git add .
git commit -m "Initial commit: Tech blog setup"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git branch -M main
git push -u origin main
```

---

## Step 2: Vercel에서 배포

1. **vercel.com** 접속
2. GitHub로 로그인 (또는 가입)
3. "Import Project" → GitHub 레포 선택
4. 설정 확인 후 "Deploy"
5. ✅ 3분 뒤 배포 완료!
   - URL: `xxx.vercel.app`

---

## Step 3: 커스텀 도메인 (선택사항)

### Vercel 도메인 무료 추가

1. Vercel 대시보드 → Settings → Domains
2. 도메인 입력
3. DNS 설정 (레포에 지침 제공됨)

### 또는 Freenom에서 무료 도메인 (선택사항)

1. freenom.com → Register → `.tk` 도메인 선택
2. 12개월 무료 등록
3. 레포 설정의 Deployment Domains에서 연결

---

## 글 작성하기

### GitHub 웹에서 직접 작성 (추천)

1. 레포 → `src/content/blog/` 폴더
2. "Add file" → "Create new file"
3. 파일명: `2024-07-25-제목.md` (날짜-제목 형식)
4. 내용 작성:

```markdown
---
title: 글 제목
description: 짧은 설명
pubDate: 2024-07-25
author: Your Name
tags: [tag1, tag2]
---

# 본문

마크다운으로 작성...
```

5. "Commit changes"
6. ✅ 1분 뒤 자동 배포!

### 또는 로컬에서 작성 후 푸시

```bash
# 글 작성 후
git add .
git commit -m "New post: 제목"
git push
```

---

## 커스터마이징

### 블로그 정보 수정

`astro.config.mjs`의 `site:` 부분을 수정하세요.

### 포트폴리오 페이지

`src/pages/portfolio.astro`에서 직접 편집 가능합니다.

### 색상/스타일 변경

각 `.astro` 파일의 `<style>` 섹션에서 CSS 수정

---

## 문제 해결

**블로그에 글이 안 보여요**
- 파일명에 `.md` 확장자가 있는지 확인
- frontmatter 형식이 맞는지 확인 (---)
- 문법 오류는 없는지 확인

**배포가 안 돼요**
- Vercel 대시보드에서 "Deployments" 탭 확인
- 빌드 로그에서 오류 메시지 확인
- GitHub 액션 탭에서 CI/CD 상태 확인

---

## 📚 더 알아보기

- [Astro 공식 문서](https://docs.astro.build)
- [Content Collections](https://docs.astro.build/en/guides/content-collections/)
- [Vercel 배포 가이드](https://vercel.com/docs)
