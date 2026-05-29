# 🏆 아메리칸 복식리그

**American Doubles League — 대진표 자동 생성 시스템**

> 파트너를 계속 바꿔가며 경기하는 아메리칸 토너먼트(American Tournament) 복식 대진표를  
> 종목과 선수 이름만 입력하면 자동으로 생성해주는 싱글 파일 웹 앱입니다.

---

## 📸 미리보기

| 설정 화면 | 대진표 | 순위표 |
|:---------:|:------:|:------:|
| 종목·인원·이름 입력 | 라운드별 경기 카드 | 실시간 승률·득실 집계 |

---

## ✨ 주요 기능

### 1. 설정 패널
- 종목 선택 — 테니스 🎾 · 배드민턴 🏸 · 탁구 🏓 · 배구 🏐
- 참가 인원 — 5명 / 6명 / 7명 / 8명
- 점수 형식 — 자유 입력 / 게임 단위 (0–6) / 랠리 포인트 (0–21)
- 선수 이름 직접 입력 (기본값 자동 채움)

### 2. 대진표 패널
- 아메리칸 방식 대진 알고리즘 자동 계산
- 라운드별 경기 카드 시각화
- + / − 버튼으로 실시간 점수 입력
- 승리 팀 골드 하이라이트 자동 적용
- 휴식 선수 표시 (5·6·7명 모드)
- 8명 모드: 2코트 동시 진행 편성
- 경기 진행률 바 실시간 반영
- **인쇄 / PDF 저장** 버튼 (브라우저 인쇄 엔진 사용 → 한글 완벽 출력)

### 3. 순위표 패널
- 승 · 패 · 득점 · 실점 · 득실 · 승률 자동 집계
- 동점 시 득실차 기준 자동 정렬
- 전체 경기 완료 시 우승자 배너 표시
- 순위표 PDF 저장 지원

---

## 🗂 대진 알고리즘

아메리칸 토너먼트는 **모든 선수가 가능한 한 다양한 파트너·상대와 경기**하도록 편성합니다.

### 5명 (4경기, 매 경기 1명 휴식)

| 경기 | 팀 A | 팀 B | 휴식 |
|:----:|:----:|:----:|:----:|
| 1경기 | A · B | C · D | E |
| 2경기 | A · C | D · E | B |
| 3경기 | A · D | B · E | C |
| 4경기 | A · E | B · C | D |

### 6명 (5경기, 매 경기 2명 대기)

| 경기 | 팀 A | 팀 B | 대기 |
|:----:|:----:|:----:|:----:|
| 1경기 | A · B | C · D | E · F |
| 2경기 | A · C | E · F | B · D |
| 3경기 | A · D | B · E | C · F |
| 4경기 | A · E | C · F | B · D |
| 5경기 | A · F | B · D | C · E |

### 7명 (7경기) · 8명 (14경기, 2코트 동시 진행)

7명 이상은 동일 원리로 자동 편성됩니다.  
8명의 경우 **코트 1 / 코트 2** 두 경기가 동시에 진행됩니다.

---

## 🖥 사용 방법

```
1. american_tournament.html 파일을 브라우저로 열기
2. 설정 탭에서 종목 · 인원 · 점수 형식 선택
3. 선수 이름 입력 후 [대진표 생성하기] 클릭
4. 대진표 탭에서 경기 결과 입력 (+/− 버튼)
5. 순위표 탭에서 실시간 순위 확인
6. [인쇄 / PDF 저장] 버튼 → 브라우저 인쇄 다이얼로그 → PDF로 저장 선택
```

> 별도 설치 불필요. 인터넷 연결 시 Google Fonts 로드 (오프라인에서도 기본 동작)

---

## 📄 PDF 저장 방법

이 앱은 **브라우저 내장 인쇄 엔진**을 사용하여 한글 깨짐 없이 PDF를 저장합니다.

```
[인쇄 / PDF 저장] 버튼 클릭
→ 브라우저 인쇄 다이얼로그 열림
→ 대상 프린터: "PDF로 저장" 또는 "Microsoft Print to PDF" 선택
→ 저장 클릭
```

- Chrome: 대상 → **PDF로 저장**
- Edge: 프린터 → **Microsoft Print to PDF**
- Firefox: 프린터 → **PDF로 저장**

---

## 🛠 기술 스택

| 항목 | 내용 |
|:-----|:-----|
| 언어 | HTML5 · CSS3 · Vanilla JavaScript (ES6+) |
| 폰트 | Bebas Neue (제목) · Noto Sans KR (본문) via Google Fonts |
| 아이콘 | Lucide Icons (inline SVG) |
| PDF | 브라우저 window.print() + @media print CSS |
| 의존성 | 없음 (단일 HTML 파일) |
| 파일 크기 | 약 50KB (단일 파일) |

---

## 📁 파일 구조

```
american_tournament.html    ← 앱 전체 (단일 파일)
README.md                   ← 이 문서
```

---

## 🎨 디자인 시스템

```css
배경색  #070707  (Pure Black)
카드    #111111  (Surface)
골드    #c8a84b  (Primary Accent)
텍스트  #f8f8f8  (Primary)
        #d4d4d4  (Secondary)
        #a8a8a8  (Muted)
승리    #52c47a  (Green)
패배    #e86060  (Red)
```

---

## 📋 점수 입력 규칙

| 형식 | 최대값 | 적용 종목 예시 |
|:-----|:------:|:-------------|
| 자유 입력 | 제한 없음 | 모든 종목 |
| 게임 단위 | 6 | 테니스 |
| 랠리 포인트 | 21 | 배드민턴 · 탁구 |

---

## 🔧 커스터마이징

`american_tournament.html` 파일을 텍스트 편집기로 열어 수정할 수 있습니다.

**선수 기본값 변경** (JavaScript 상단)
```javascript
const DF = ['김민준', '이서연', '박지호', '최유나', '정태양', '오하늘', '윤소현', '강민혁'];
```

**아바타 색상 변경**
```javascript
const AVC = ['#c8a84b', '#5090e8', '#52c47a', '#e86060', ...];
```

**종목 추가**
```javascript
const SN = { tennis:'테니스', badminton:'배드민턴', pingpong:'탁구', volleyball:'배구', myGame:'내 종목' };
```

---

## 🚀 배포 (GitHub Pages)

```bash
# 1. GitHub 저장소 생성 후 파일 업로드
git init
git add american_tournament.html README.md
git commit -m "init: 아메리칸 복식리그 앱"
git push origin main

# 2. Settings → Pages → Branch: main → Save
# 3. 접속 URL 확인
# https://[username].github.io/[repo-name]/american_tournament.html
```

QR코드 생성기([qr-code-generator.com](https://www.qr-code-generator.com))로 URL을  
QR코드로 변환하면 현장에서 참가자들이 스마트폰으로 즉시 접속할 수 있습니다.

---

## 📱 지원 환경

| 환경 | 지원 |
|:-----|:----:|
| Chrome (PC) | ✅ |
| Edge (PC) | ✅ |
| Firefox (PC) | ✅ |
| Safari (Mac) | ✅ |
| Chrome (모바일) | ✅ |
| Safari (iOS) | ✅ |

---

## 📝 변경 이력

| 버전 | 날짜 | 내용 |
|:----:|:----:|:-----|
| v1.0 | 2025.05 | 최초 릴리즈 — 5·6명 대진표 |
| v1.1 | 2025.05 | 7·8명 지원, 점수 형식 추가 |
| v1.2 | 2025.05 | Lucide 아이콘, 한글 PDF 해결, 디자인 개선 |

---

## 👤 저작자

```
© Produced by You Seung-oh
아메리칸 복식리그 — American Doubles League
```

---

## 📜 라이선스

개인 및 교육 목적 자유 사용 가능.  
상업적 이용 및 재배포 시 저작자 표시 필요.

---

<div align="center">

**아메리칸 복식리그** · American Doubles League

*종목과 이름만 입력하면, 대진표는 자동으로.*

</div>
