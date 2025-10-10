# Orchwang Devlog - Project Blueprint

## 📋 Table of Contents

- [Vision & Purpose](#vision--purpose)
- [Content Architecture](#content-architecture)
- [Technical Stack](#technical-stack)
- [Content Guidelines](#content-guidelines)
- [Development Workflow](#development-workflow)
- [Quality Standards](#quality-standards)
- [Future Roadmap](#future-roadmap)

---

## 🎯 Vision & Purpose

### Mission Statement

개발자 "황오크(Orchwang)"의 기술 성장과 학습 여정을 체계적으로 기록하고 공유하는 개인 기술 블로그입니다.

### Core Objectives

1. **학습 기록 (Learning Journal)**
   - 개발자로서의 기술 학습 과정을 문서화
   - 실무 경험과 프로젝트에서 얻은 인사이트 공유
   - 문제 해결 과정과 해결책 아카이브

2. **역량 정의 및 추적 (Competency Framework)**
   - 연차별/레벨별 개발자 역량 프레임워크 정의
   - 자기 평가 및 성장 지표 관리
   - 체계적인 커리어 발전 로드맵 수립

3. **지식 공유 (Knowledge Sharing)**
   - Python 백엔드 엔지니어링 심화 지식
   - 아키텍처 설계 및 시스템 최적화 경험
   - 기술 리더십 및 협업 노하우

### Target Audience

- **Primary**: 본인의 학습 및 성장 기록
- **Secondary**: Python 백엔드 엔지니어를 목표로 하는 개발자
- **Tertiary**: 기술 리더십과 시니어 역량에 관심 있는 개발자

### Key Reference

본 블로그의 핵심 역량 프레임워크는 다음 문서를 기준으로 합니다:
- `data/blog/career/technical-competencies-for-python-engineer.mdx`
- `data/blog/career/python-engineer-job-description.mdx`
- `data/blog/python/python-overall-curriculum.mdx`

---

## 📁 Content Architecture

### Content Categories

#### 1. **Career** (`data/blog/career/`)
**목적**: 개발자 커리어 발전과 역량 관리

**주요 콘텐츠**:
- 파이썬 백엔드 엔지니어 기술 역량 프레임워크
- 자기평가표 (Skill Self-Assessment Checklist)
- 직무 기술서 (Job Description by Level)
- 레벨별 성장 로드맵

**Tags**: `career`, `competency`, `leadership`

#### 2. **Python** (`data/blog/python/`)
**목적**: Python 심화 학습 및 엔지니어링 지식

**주요 콘텐츠**:
- Python Internals 및 성능 최적화
- 고급 동시성 모델 (asyncio, multiprocessing)
- 아키텍처 패턴 (DDD, CQRS)
- 실무 프로젝트 케이스 스터디

**Tags**: `python`, `backend`, `architecture`, `performance`

#### 3. **Diary** (`data/blog/diary/`)
**목적**: 개인 회고 및 성찰

**주요 콘텐츠**:
- 연도별 회고 (Retrospective)
- 분기별/월별 학습 리뷰
- 개인 프로젝트 진행 기록

**Tags**: `diary`, `retrospective`, `reflection`

#### 4. **Planning** (`data/blog/planning/`)
**목적**: 목표 설정 및 계획 수립

**주요 콘텐츠**:
- 연간 목표 및 OKR
- 학습 계획 및 로드맵
- 커리어 발전 전략

**Tags**: `planning`, `goals`, `roadmap`

#### 5. **Book** (`data/blog/book/`)
**목적**: 독서 기록 및 서평

**주요 콘텐츠**:
- 기술 서적 리뷰
- 핵심 개념 요약
- 실무 적용 인사이트

**Tags**: `book`, `review`, `learning`

### Content Organization

```
data/blog/
├── career/           # 커리어 & 역량 관리
├── python/           # Python 기술 심화
├── diary/            # 개인 회고
├── planning/         # 목표 & 계획
└── book/             # 독서 & 서평
```

### Metadata Standard

모든 블로그 포스트는 다음 frontmatter 메타데이터를 포함해야 합니다:

```yaml
---
title: "포스트 제목"
date: 'YYYY-MM-DD'
tags: ['tag1', 'tag2', 'tag3']
draft: false
summary: "포스트 요약 (1-2 문장, 한글 150자 이내)"
images: []
---
```

**필수 필드**:
- `title`: 포스트 제목
- `date`: 작성일 (ISO 8601 형식)
- `tags`: 태그 배열 (최소 1개, 권장 2-3개)
- `draft`: 초안 여부 (boolean)
- `summary`: 포스트 요약

**선택 필드**:
- `images`: 대표 이미지 경로 배열
- `authors`: 작성자 (기본값: 'default')
- `layout`: 레이아웃 템플릿
- `canonicalUrl`: SEO용 정규 URL

---

## 🛠 Technical Stack

### Framework & Core

| Technology | Version | Purpose |
|-----------|---------|---------|
| Next.js | 14.2.33 | React 기반 프레임워크, SSG/SSR |
| React | 18.3.1 | UI 라이브러리 |
| TypeScript | 5.9.3 | 타입 안전성 |
| Node.js | Latest LTS | 런타임 환경 |

### Content Management

| Technology | Version | Purpose |
|-----------|---------|---------|
| Contentlayer | 0.3.4 | MDX 콘텐츠 관리 |
| next-contentlayer | 0.3.4 | Next.js + Contentlayer 통합 |
| gray-matter | 4.0.3 | Frontmatter 파싱 |
| reading-time | 1.5.0 | 읽기 시간 계산 |

### Styling & UI

| Technology | Version | Purpose |
|-----------|---------|---------|
| Tailwind CSS | 3.4.18 | 유틸리티 CSS 프레임워크 |
| @tailwindcss/typography | 0.5.19 | 타이포그래피 플러그인 |
| @tailwindcss/forms | 0.5.10 | 폼 스타일링 |
| next-themes | 0.4.6 | 다크 모드 지원 |

### MDX Processing

**Remark Plugins** (Markdown → MDAST):
- `remark-gfm` 3.0.1: GitHub Flavored Markdown
- `remark-math` 5.1.1: 수학 표현식 지원

**Rehype Plugins** (MDAST → HTML):
- `rehype-slug` 5.1.0: 헤딩 ID 자동 생성
- `rehype-autolink-headings` 6.1.1: 헤딩 자동 링크
- `rehype-katex` 6.0.3: 수학 렌더링
- `rehype-prism-plus` 1.6.3: 코드 신택스 하이라이팅
- `rehype-citation` 1.0.3: 인용 및 참고문헌
- `rehype-mermaidjs` 2.0.0: Mermaid 다이어그램
- `rehype-preset-minify` 6.0.0: HTML 압축

### Blog Framework

| Technology | Version | Purpose |
|-----------|---------|---------|
| Pliny | 0.4.1 | 블로그 기능 통합 (검색, 댓글, 분석) |

### Development Tools

| Technology | Version | Purpose |
|-----------|---------|---------|
| ESLint | 8.57.1 | 코드 린팅 |
| Prettier | 3.6.2 | 코드 포맷팅 |
| Husky | 8.0.3 | Git hooks |
| lint-staged | 13.3.0 | 스테이지된 파일 린팅 |
| cross-env | 7.0.3 | 환경변수 크로스 플랫폼 |

### Build Tools

| Technology | Version | Purpose |
|-----------|---------|---------|
| esbuild | 0.25.10 | 고속 번들러 |
| PostCSS | 8.5.6 | CSS 처리 |
| Autoprefixer | 10.4.21 | CSS vendor prefix 자동화 |

### Package Manager

- **Yarn** 3.6.1 (Modern Yarn / Berry)

---

## 📝 Content Guidelines

### Writing Principles

1. **명확성 (Clarity)**
   - 기술 용어는 처음 사용 시 설명 추가
   - 복잡한 개념은 예제와 함께 설명
   - 단계별로 구조화된 설명

2. **실용성 (Practicality)**
   - 이론보다 실무 적용 가능한 내용 우선
   - 실제 코드 예제 포함
   - 문제 해결 과정 중심 서술

3. **체계성 (Structure)**
   - 일관된 포스트 구조 유지
   - 목차 및 섹션 구분 명확화
   - 적절한 헤딩 레벨 사용 (##, ###)

4. **진정성 (Authenticity)**
   - 실제 경험과 학습 과정 공유
   - 실패 사례 및 교훈 포함
   - 개인적 인사이트 강조

### Post Structure

권장 포스트 구조:

```markdown
---
frontmatter
---

## 서론
- 배경 및 맥락
- 주요 학습 목표

## 본론
- 핵심 내용 (섹션별 구분)
- 코드 예제
- 실습 과정

## 결론
- 핵심 요약
- 얻은 인사이트
- 다음 단계

## 참고 자료
- 관련 링크 및 문서
```

### Markdown/MDX Formatting

1. **헤딩 (Headings)**
   - `#`는 사용하지 않음 (title이 H1)
   - `##`부터 시작
   - 섹션 구분은 `---` 사용

2. **코드 블록**
   ```python
   # 언어 지정 필수
   def example():
       pass
   ```

3. **표 (Tables)**
   - Markdown 표 문법 사용
   - 헤더 행 포함 필수
   ```markdown
   | 컬럼1 | 컬럼2 |
   |------|------|
   | 값1  | 값2  |
   ```

4. **목록 (Lists)**
   - 순서 없는 목록: `-` 사용
   - 순서 있는 목록: `1.`, `2.` 사용
   - 중첩 시 2칸 들여쓰기

5. **강조**
   - **굵게**: `**텍스트**`
   - *기울임*: `*텍스트*`
   - `코드`: `` `코드` ``

### Code Examples

1. **완전한 예제 제공**
   - 실행 가능한 코드
   - 필요한 import 문 포함

2. **주석 활용**
   - 핵심 로직에 주석 추가
   - 복잡한 부분 설명

3. **출력 결과 포함**
   ```python
   # 예제 실행 결과:
   # Output: [1, 2, 3]
   ```

---

## 🔄 Development Workflow

### Available Scripts

```bash
# 개발 서버 실행 (포트 3111)
yarn start

# 개발 서버 (기본 포트)
yarn dev

# 프로덕션 빌드
yarn build

# 프로덕션 서버 실행
yarn serve

# 번들 분석
yarn analyze

# 린팅 및 자동 수정
yarn lint
```

### Development Process

1. **콘텐츠 작성**
   ```bash
   # 새 포스트 생성
   data/blog/{category}/{slug}.mdx

   # frontmatter 작성
   # 본문 작성 (Markdown/MDX)
   ```

2. **로컬 테스트**
   ```bash
   yarn start
   # http://localhost:3111 확인
   ```

3. **품질 검사**
   ```bash
   yarn lint
   # ESLint + Prettier 자동 수정
   ```

4. **빌드 확인**
   ```bash
   yarn build
   # 빌드 에러 확인
   ```

### Git Workflow

1. **Pre-commit Hooks** (Husky)
   - 자동 lint 및 format 실행
   - 스테이지된 파일만 처리

2. **Lint-staged**
   - `*.ts`, `*.tsx`: ESLint 자동 수정
   - 모든 파일: Prettier 포맷팅

### Environment Variables

`.env` 파일 구조:
```bash
# 필요한 환경변수 정의
# (실제 값은 .env.example 참조)
```

---

## ✅ Quality Standards

### Code Quality

1. **TypeScript**
   - Strict 모드 활성화
   - 타입 안전성 유지
   - any 타입 최소화

2. **ESLint**
   - Next.js 규칙 준수
   - Prettier 통합
   - 자동 수정 가능한 규칙 활성화

3. **Formatting**
   - Prettier 자동 포맷팅
   - Tailwind CSS 클래스 정렬
   - 일관된 코드 스타일

### Content Quality

1. **메타데이터 완성도**
   - 모든 필수 필드 작성
   - 의미 있는 summary 제공
   - 적절한 태그 선택

2. **가독성**
   - 명확한 제목 및 섹션 구분
   - 적절한 단락 나누기
   - 코드 예제 포함

3. **SEO 최적화**
   - 검색 친화적 제목
   - 메타 설명 최적화
   - 적절한 헤딩 구조

### Performance

1. **빌드 최적화**
   - Static Generation (SSG) 활용
   - 이미지 최적화 (next/image)
   - 코드 스플리팅

2. **번들 크기**
   - 불필요한 의존성 제거
   - Tree-shaking 활용
   - 번들 분석 정기 실행

---

## 🚀 Future Roadmap

### Short-term (3 months)

- [ ] 주차별 Python 심화 학습 시리즈 완성
- [ ] 분기별 회고 작성 체계화
- [ ] 코드 예제 GitHub 레포지토리 연동
- [ ] 검색 기능 개선 (Algolia/Kbar)

### Mid-term (6 months)

- [ ] 아키텍처 설계 케이스 스터디 시리즈
- [ ] 성능 최적화 실습 프로젝트 문서화
- [ ] 인터랙티브 코드 플레이그라운드 추가
- [ ] 댓글 기능 통합 (Giscus)

### Long-term (1 year)

- [ ] Next.js 15 및 React 19 마이그레이션
- [ ] Tailwind CSS 4 업그레이드
- [ ] 다국어 지원 (한/영)
- [ ] Newsletter 구독 기능
- [ ] 포트폴리오 섹션 추가

### Content Expansion

- [ ] 시스템 디자인 시리즈
- [ ] 팀 리더십 및 멘토링 경험 공유
- [ ] 오픈소스 기여 사례
- [ ] 기술 컨퍼런스 발표 자료

### Technical Improvements

- [ ] CI/CD 파이프라인 구축
- [ ] 자동화된 테스트 추가
- [ ] 성능 모니터링 도구 통합
- [ ] 접근성 (A11y) 개선

---

## 📚 References

### Related Documents

- `README.md`: 프로젝트 개요 및 시작 가이드
- `data/siteMetadata.js`: 사이트 설정
- `contentlayer.config.ts`: 콘텐츠 레이어 설정

### External Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS](https://tailwindcss.com)
- [Contentlayer](https://contentlayer.dev)
- [Tailwind Nextjs Starter Blog](https://github.com/timlrx/tailwind-nextjs-starter-blog)

---

**Last Updated**: 2025-10-10
**Version**: 1.0.0
**Maintainer**: 황오크 (Orchwang)
